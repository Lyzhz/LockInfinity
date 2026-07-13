# LockInfinity

Sistema de gerenciamento de armários inteligentes com comunicação Bluetooth Low Energy (BLE), interface administrativa avançada e layout dinâmico baseado em grid flexível.

---

# Visão Geral

O LockInfinity foi desenvolvido para oferecer uma experiência moderna e escalável na gestão de armários inteligentes, permitindo configurações personalizadas de layout, controle de acesso simplificado e administração centralizada.

A nova arquitetura introduz um sistema de posicionamento flexível semelhante a um grid estilo "Tetris", possibilitando armários de diferentes dimensões e melhor aproveitamento do espaço disponível.

---

# Principais Funcionalidades

## Grid Inteligente e Flexível

* Suporte a armários de múltiplos tamanhos (1×1 até 4×3 células)
* Posicionamento livre através de linhas e colunas configuráveis
* Rolagem horizontal para otimização da área útil
* Interface responsiva adaptada ao tamanho de cada armário
* Melhor aproveitamento visual para instalações de grande porte

## Administração Avançada

Painel administrativo protegido por autenticação para gerenciamento completo dos armários.

### Recursos disponíveis

* Criação de novos armários
* Exclusão de armários existentes
* Alteração de nome e identificação
* Configuração de comandos BLE
* Ajuste de posição no grid
* Definição de largura e altura
* Ativação de modo manutenção
* Desabilitação de armários
* Abertura forçada para emergências

## Interface Moderna

* Layout com identidade visual profissional
* Fundo com gradiente institucional
* Indicadores visuais por status
* Transições e animações suaves
* Painel de usuário com feedback em tempo real
* Contadores e métricas atualizados dinamicamente

---

# Arquitetura do Projeto

```text
lib/
├── core/
│   └── ble_service.dart
│
├── features/
│   ├── lockers/
│   │   ├── locker_model.dart
│   │   ├── locker_repository.dart
│   │   ├── locker_controller.dart
│   │   ├── locker_card.dart
│   │   ├── locker_grid.dart
│   │   ├── lockers_page.dart
│   │   └── user_info_panel.dart
│   │
│   ├── admin/
│   │   └── admin_page.dart
│   │
│   ├── scan/
│   │   └── scan_page.dart
│   │
│   └── config/
│       └── config_page.dart
│
├── shared/
│   └── theme/
│       └── app_theme.dart
│
└── main.dart
```

---

# Tecnologias Utilizadas

* Flutter 3.2.3+
* Dart
* flutter_reactive_ble
* shared_preferences
* another_flushbar

---

# Instalação

## Pré-requisitos

* Flutter SDK instalado
* Android SDK configurado
* Dispositivo Android ou emulador

## Execução

```bash
flutter pub get
flutter run
```

---

# Controle de Acesso

| Área                      | Senha  |
| ------------------------- | ------ |
| Administração de Armários | 512515 |

**Observação:** O acesso é realizado mantendo pressionado o logotipo da aplicação.

---

# Configuração de Armários

1. Acesse o painel administrativo.
2. Selecione o armário desejado.
3. Configure os seguintes parâmetros:

### Informações Básicas

* Nome do armário
* Comando BLE associado

### Posicionamento

* Linha (Row)
* Coluna (Column)

### Dimensões

* Largura (Width Span)
* Altura (Height Span)

As alterações são persistidas automaticamente.

---

# Exemplos de Layout

## Layout Tradicional

32 armários padrão organizados em grade uniforme.

```text
Linha 0: Armários 1–8
Linha 1: Armários 9–16
Linha 2: Armários 17–24
Linha 3: Armários 25–32
```

## Layout Híbrido

Combinação de armários convencionais e ampliados.

```text
Linha 0, Coluna 0 → Armário 1 (2×2)
Linha 0, Coluna 2 → Armário 2 (1×1)
Linha 0, Coluna 3 → Armário 3 (1×3)
Linha 1, Coluna 0 → Armário 4 (3×1)
```

---

# Fluxo Operacional

1. O usuário aproxima seu crachá NFC.
2. O sistema identifica e valida o usuário.
3. Os dados são exibidos no painel superior.
4. O usuário seleciona o armário desejado.
5. O comando é enviado via BLE.
6. O armário é travado ou destravado.
7. Após 12 segundos de inatividade, o sistema limpa automaticamente os dados do usuário.

---

# Status dos Armários

| Status       | Cor      | Descrição                    |
| ------------ | -------- | ---------------------------- |
| Livre        | Verde    | Disponível para utilização   |
| Ocupado      | Vermelho | Em uso por um usuário        |
| Manutenção   | Laranja  | Temporariamente indisponível |
| Desabilitado | Cinza    | Bloqueado para operação      |

---

# Roadmap

## Próximas Evoluções

* Drag & Drop para reorganização do grid
* Importação e exportação de layouts
* Pré-visualização gráfica no painel administrativo
* Histórico de utilização por armário
* Integração com APIs corporativas
* Suporte a tema claro e escuro
* Dashboard operacional com métricas de uso
* Controle de permissões por perfil de usuário

---

# Solução de Problemas

## Grid não exibe todos os armários

* Verifique a rolagem horizontal.
* Ajuste o tamanho dos armários configurados.

## Problemas de conexão BLE

* Confirme as permissões de Bluetooth e Localização.
* Reinicie a conexão através da tela de escaneamento.
* Verifique se o dispositivo BLE está energizado e dentro do alcance.

---

# LockInfinity v1.0.0

Plataforma inteligente para gerenciamento de armários corporativos, desenvolvida para oferecer flexibilidade operacional, facilidade de administração e integração com dispositivos BLE de forma segura e escalável.
