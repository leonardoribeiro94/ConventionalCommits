🧭 Guia de Commit Semantics (Conventional Commits)

Padrão recomendado para manter histórico de commits limpo, rastreável e automatizável (ex: changelog, semantic versioning e release pipelines).

🧩 Estrutura do Commit

Cada commit deve seguir o formato:

<type>(<scope>): <short summary>


🔹 O campo <scope> é opcional, mas recomendado.
🔹 O resumo deve ser em minúsculas, claro e direto.
🔹 Use o imperativo (“add”, “fix”, “update”), não o passado (“added”, “fixed”).

🏷️ Principais Tipos de Commit
Tipo	Uso	Exemplo
feat	Adição de nova funcionalidade	feat(auth): add JWT authentication middleware
fix	Correção de bug	fix(user): handle null email validation
chore	Tarefas de manutenção (build, deps, scripts)	chore(deps): bump EF Core to 8.0.3
docs	Alterações apenas em documentação	docs(readme): update setup instructions
style	Mudanças de formatação (sem impacto lógico)	style(api): format controller methods
refactor	Refatoração sem alterar comportamento	refactor(repository): simplify Dapper queries
perf	Melhorias de performance	perf(cache): optimize response serialization
test	Adição ou ajuste de testes	test(service): add integration tests for appointment flow
build	Mudanças em build, CI/CD, pipelines	build(ci): add Docker image publish step
ci	Alterações específicas de integração contínua	ci(github): update actions version
revert	Reversão de commit anterior	revert: revert "feat(auth): add JWT support"
🧠 Exemplo Completo
feat(user): create endpoint for user registration


Descrição:

feat → nova feature

user → escopo da alteração

mensagem → ação realizada

💬 Mensagem adicional (opcional):

feat(user): create endpoint for user registration

- Added POST /api/v1/users endpoint
- Integrated with service layer and validation
- Updated Swagger documentation

Closes #4215

🧱 Scopes Recomendados (exemplo de projeto .NET)
Camada	Escopo sugerido
Domain	domain
Application	app
Infrastructure	infra
Presentation / Api	api
Tests	tests
DevOps	ci, build, helm, docker
⚙️ Boas Práticas

Commits pequenos e atômicos – uma única intenção por commit.

Usar inglês técnico – facilita colaboração global e automação.

Não use ponto final na mensagem curta.

Mantenha até 72 caracteres na linha de resumo.

Conecte issues (Closes #123, Refs #456).

Evite commits genéricos: ❌ “update code”, “fix bug”, “changes”.

🚀 Exemplos Reais
feat(api): add endpoint to schedule appointments
fix(infra): correct connection string for PostgreSQL
refactor(domain): extract validation logic from entity
chore(docker): update base image to dotnet/sdk:8.0
docs(readme): include setup instructions for local dev
test(app): add unit tests for StoreService

🔄 Automatização (Dica Extra)

Com Conventional Commits bem aplicados, é possível:

Gerar CHANGELOG automático com semantic-release ou commitlint.

Automatizar versionamento major.minor.patch.

Impor padrão com commitlint + Husky:

Exemplo de .commitlintrc.json:

{
  "extends": ["@commitlint/config-conventional"]
}

🏁 Resumo Visual
feat       → nova funcionalidade
fix        → correção de bug
docs       → documentação
style      → formatação
refactor   → refatoração sem mudança funcional
perf       → otimização de performance
test       → testes automatizados
chore      → manutenção geral
build/ci   → automação e deploy
