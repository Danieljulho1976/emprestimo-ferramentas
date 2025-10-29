# Welcome to your Lovable project

## Project info

**URL**: https://lovable.dev/projects/f9f48b2b-8ac7-46b5-b818-81058092fff1

## How can I edit this code?

There are several ways of editing your application.

**Use Lovable**

Simply visit the [Lovable Project](https://lovable.dev/projects/f9f48b2b-8ac7-46b5-b818-81058092fff1) and start prompting.

Changes made via Lovable will be committed automatically to this repo.

**Use your preferred IDE**

If you want to work locally using your own IDE, you can clone this repo and push changes. Pushed changes will also be reflected in Lovable.

The only requirement is having Node.js & npm installed - [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating)

Follow these steps:

```sh
# Step 1: Clone the repository using the project's Git URL.
git clone <YOUR_GIT_URL>

# Step 2: Navigate to the project directory.
cd <YOUR_PROJECT_NAME>

# Step 3: Install the necessary dependencies.
npm i

# Step 4: Start the development server with auto-reloading and an instant preview.
npm run dev
```

**Edit a file directly in GitHub**

- Navigate to the desired file(s).
- Click the "Edit" button (pencil icon) at the top right of the file view.
- Make your changes and commit the changes.

**Use GitHub Codespaces**

- Navigate to the main page of your repository.
- Click on the "Code" button (green button) near the top right.
- Select the "Codespaces" tab.
- Click on "New codespace" to launch a new Codespace environment.
- Edit files directly within the Codespace and commit and push your changes once you're done.

## What technologies are used for this project?

This project is built with:

- Vite
- TypeScript
- React
- shadcn-ui
- Tailwind CSS
- Supabase (Backend/Database)

## Supabase Configuration

The project uses Supabase as the backend. To set up:

1. Create a `.env` file in the project root with:
```env
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

2. Database Schema:

### Table: tool_categories
- id: uuid (primary key)
- created_at: timestamp
- name: text (unique)
- description: text

### Table: tools
- id: uuid (primary key)
- created_at: timestamp
- name: text
- description: text
- status: enum (available, in_use, maintenance, lost)
- category_id: uuid (foreign key -> tool_categories.id)
- acquisition_date: date
- last_maintenance: timestamp
- next_maintenance: timestamp
- serial_number: text (unique)
- location: text

### Table: employees
- id: uuid (primary key)
- created_at: timestamp
- name: text
- email: text (unique)
- department: text
- position: text
- status: enum (active, inactive)
- phone: text
- hire_date: date
- badge_number: text (unique)

### Table: loans
- id: uuid (primary key)
- created_at: timestamp
- tool_id: uuid (foreign key -> tools.id)
- employee_id: uuid (foreign key -> employees.id)
- checkout_date: timestamp
- expected_return_date: timestamp
- return_date: timestamp
- status: enum (active, returned, overdue)
- notes: text
- condition_on_checkout: text
- condition_on_return: text

### Views
- active_loans_view: View consolidada de empréstimos ativos com informações de ferramentas e colaboradores

### Functions
- is_tool_available(tool_uuid): Verifica se uma ferramenta está disponível para empréstimo
- update_overdue_loans(): Atualiza automaticamente status de empréstimos vencidos
- update_tool_status(): Trigger para atualizar status da ferramenta conforme empréstimos

### Features
- Enums para garantir consistência de status
- Índices otimizados para consultas frequentes
- Triggers automáticos para manutenção de status
- Validações de unicidade (serial_number, email, badge_number)
- Controle automático de empréstimos vencidos
- Rastreamento de condições de ferramentas na entrada/saída

## How can I deploy this project?

Simply open [Lovable](https://lovable.dev/projects/f9f48b2b-8ac7-46b5-b818-81058092fff1) and click on Share -> Publish.

## Can I connect a custom domain to my Lovable project?

Yes, you can!

To connect a domain, navigate to Project > Settings > Domains and click Connect Domain.

Read more here: [Setting up a custom domain](https://docs.lovable.dev/features/custom-domain#custom-domain)

Nome do Banco Supabase: Emprestimo_Ferramentas_2025
Usuário: Controle-Estoque-CHS-Sorocaba
Email Primário: seconcichs@gmail.com
https://supabase.com/dashboard/project/jimfxcilgcsufobxumkp
Organization: Preventivas_2025
Github: https://github.com/Danieljulho1976
