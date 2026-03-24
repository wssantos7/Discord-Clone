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

<div class="flex h-screen w-full bg-[#313338] text-[#dbdee1] overflow-hidden">
  
  <nav class="w-[72px] bg-[#1e1f22] flex flex-col items-center py-3 space-y-2">
    <div class="w-12 h-12 bg-[#5865f2] rounded-[16px] flex items-center justify-center text-white">
      </div>
    <hr class="w-8 border-t-2 border-[#35363c] rounded-full" />
    </nav>

  <aside class="w-60 bg-[#2b2d31] flex flex-col">
    <header class="h-12 px-4 flex items-center border-b border-[#1e1f22] font-bold shadow-sm">
      Nome do Servidor
    </header>
    <div class="flex-1 overflow-y-auto p-2">
      <div class="text-xs uppercase font-bold text-[#949ba4] px-2 mb-1">Canais de Texto</div>
      <div class="bg-[#3f4147] text-white px-2 py-1 rounded hover:bg-[#35373c] cursor-pointer">
        # general
      </div>
    </div>
  </aside>

  <main class="flex-1 flex flex-col">
    <header class="h-12 px-4 flex items-center border-b border-[#1e1f22] shadow-sm">
      # general
    </header>
    <div class="flex-1 p-4 overflow-y-auto">
      </div>
    <div class="px-4 pb-6">
      <div class="bg-[#383a40] rounded-lg p-3">
        <input type="text" placeholder="Conversar em #general" class="bg-transparent w-full outline-none" />
      </div>
    </div>
  </main>

</div>
