# 🎮 SyncChord - Fullstack Discord Clone

![Banner do Projeto](https://raw.githubusercontent.com/shadcn-ui/ui/main/apps/www/public/og.jpg) SyncChord é uma plataforma de comunicação em tempo real inspirada no Discord, construída com foco em performance, escalabilidade e uma experiência de usuário fluida. 

---

## ✨ Funcionalidades

* **🌐 Servidores Personalizados:** Crie, edite e gerencie seus próprios servidores com convites únicos.
* **💬 Canais Dinâmicos:** Suporte para canais de **Texto, Áudio e Vídeo** (via LiveKit/WebRTC).
* **⚡ Real-time Messaging:** Chat instantâneo utilizando **Socket.io**.
    * Edição e exclusão de mensagens em tempo real.
    * Upload de anexos (Imagens e PDFs).
* **🛡️ Sistema de Permissões:** Cargos de Administrador, Moderador e Convidado (RBAC).
* **🌓 Design Responsivo:** Totalmente adaptado para Dark e Light mode com **Tailwind CSS**.
* **🔍 Busca Global:** Encontre canais e membros rapidamente.

---

## 🛠️ Tecnologias Utilizadas

| Camada | Tecnologia |
| :--- | :--- |
| **Framework** | [Next.js 15 (App Router)](https://nextjs.org/) |
| **Estilização** | [Tailwind CSS](https://tailwindcss.com/) + [Shadcn/UI](https://ui.shadcn.com/) |
| **Banco de Dados** | [PostgreSQL](https://www.postgresql.org/) (via Supabase/Neon) |
| **ORM** | [Prisma](https://www.prisma.io/) |
| **Autenticação** | [Clerk](https://clerk.com/) |
| **Real-time** | [Socket.io](https://socket.io/) |
| **Mídia (Voz/Vídeo)** | [LiveKit](https://livekit.io/) |

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
* Node.js 18+ 
* Uma conta no [Clerk](https://clerk.com/) para autenticação.
* Uma instância de PostgreSQL (recomendo Supabase).

### Passo a Passo

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/seu-usuario/syncchord.git](https://github.com/seu-usuario/syncchord.git)
   cd syncchord
