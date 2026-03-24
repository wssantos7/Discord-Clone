// Localização: prisma/schema.prisma

generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

enum MemberRole {
  ADMIN
  MODERATOR
  GUEST
}

model Profile {
  id       String @id @default(uuid())
  userId   String @unique
  name     String
  imageUrl String @db.Text
  email    String @db.Text

  servers  Server[]
  members  Member[]
  channels Channel[]

  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}

model Server {
  id         String @id @default(uuid())
  name       String
  imageUrl   String @db.Text
  inviteCode String @unique

  profileId String
  profile   Profile @relation(fields: [profileId], references: [id], onDelete: Cascade)

  members  Member[]
  channels Channel[]

  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt

  @@index([profileId])
}

model Member {
  id   String     @id @default(uuid())
  role MemberRole @default(GUEST)

  profileId String
  profile   Profile @relation(fields: [profileId], references: [id], onDelete: Cascade)

  serverId String
  server   Server @relation(fields: [serverId], references: [id], onDelete: Cascade)

  messages Message[]
  directMessages DirectMessage[]

  conversationsInitiated Conversation[] @relation("MemberOne")
  conversationsReceived  Conversation[] @relation("MemberTwo")

  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt

  @@index([profileId])
  @@index([serverId])
}

enum ChannelType {
  TEXT
  AUDIO
  VIDEO
}

model Channel {
  id   String      @id @default(uuid())
  name String
  type ChannelType @default(TEXT)

  profileId String
  profile   Profile @relation(fields: [profileId], references: [id], onDelete: Cascade)

  serverId String
  server   Server @relation(fields: [serverId], references: [id], onDelete: Cascade)

  messages Message[]

  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt

  @@index([profileId])
  @@index([serverId])
}

model Message {
  id      String @id @default(uuid())
  content String @db.Text

  fileUrl String? @db.Text

  memberId String
  member   Member @relation(fields: [memberId], references: [id], onDelete: Cascade)

  channelId String
  channel   Channel @relation(fields: [channelId], references: [id], onDelete: Cascade)

  deleted Boolean @default(false)

  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt

  @@index([channelId])
  @@index([memberId])
}

syncchord/
├── app/                  # Rotas do Next.js (App Router)
│   ├── (auth)/           # Login e Registro (Clerk)
│   ├── (main)/           # Layout principal do App
│   │   ├── servers/
│   │   │   └── [serverId]/
│   │   │       ├── channels/[channelId]/
│   │   │       └── layout.tsx
│   └── api/              # Endpoints (Socket.io, Webhooks)
├── components/           # Componentes Shadcn/UI
│   ├── server/           # Sidebar do servidor e busca
│   ├── navigation/       # Barra lateral esquerda (ícones de servidores)
│   ├── chat/             # Input de texto, mensagens e cabeçalho
│   └── modals/           # Modais de criar servidor, convidar, etc.
├── hooks/                # Custom hooks (useSocket, useModal)
├── lib/                  # Configurações (db.ts, utils.ts)
└── public/               # Ativos estáticos# Discord-Clone
