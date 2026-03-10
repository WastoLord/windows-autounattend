# 🖥️ Windows Auto Setup — autounattend.xml

Instalação automatizada e otimizada do Windows 10/11, sem cliques, sem bloatware, sem telemetria. Pronto pra uso profissional em assistência técnica.

---

## ✅ O que esse projeto faz

- Instala o Windows completamente sem interação do usuário
- Remove todos os aplicativos inúteis que vêm por padrão (Teams, Cortana, Copilot, OneDrive, Clipchamp, etc.)
- Desativa telemetria, rastreamento e envio de dados para a Microsoft
- Configura o sistema para máxima performance (Ultimate Performance power scheme)
- Instala automaticamente os programas essenciais a partir de um pendrive:
  - Google Chrome
  - Visual C++ Redistributable
  - .NET Framework
  - Microsoft Office 365
- Aplica configurações de privacidade, registro e UX logo na primeira inicialização
- Funciona 100% offline — sem precisar de internet durante a instalação

---

## 📁 Estrutura do Pendrive

```
📁 Pendrive
├── autounattend.xml
└── 📁 extras
    ├── chrome_installer.exe
    ├── vc_redist.x64.exe
    ├── ndp48-x86-x64-allos-enu.exe
    └── office365.exe
```

---

## 🚀 Como usar

**1.** Baixe ou crie uma ISO do Windows 10 ou 11 (qualquer edição)

**2.** Grave a ISO em um pendrive com [Rufus](https://rufus.ie) ou [Ventoy](https://ventoy.net)

**3.** Copie o `autounattend.xml` para a raiz do pendrive

**4.** Crie a pasta `extras` no pendrive e coloque os instaladores dentro

**5.** Boot pelo pendrive — a instalação roda sozinha até a área de trabalho

> ⚠️ **Atenção:** O processo formata o disco. Faça backup antes de usar.

---

## 🔧 O que é configurado automaticamente

### Sistema
- Idioma e região: Português (Brasil)
- Fuso horário automático
- Política de senhas sem expiração
- Caminhos longos habilitados (LongPathsEnabled)
- Fast Startup desativado
- Hibernação desativada
- Menu de contexto clássico restaurado

### Performance
- Ultimate Performance power scheme ativado
- SysMain (Superfetch) desativado
- Windows Search indexer desativado
- Serviços desnecessários desativados

### Privacidade
- Telemetria zerada (AllowTelemetry = 0)
- Cortana desativada
- Copilot removido
- Windows Recall desativado
- Localização desativada
- Advertising ID desativado
- Activity Feed desativado
- Sincronização de configurações desativada
- Bing nos resultados de pesquisa desativado

### Interface
- Extensões de arquivo visíveis
- Arquivos ocultos visíveis
- Botão de pesquisa removido da barra de tarefas
- Task View removido da barra de tarefas
- Widgets desativados
- Start Menu sem pins (limpo)
- Windows Photo Viewer restaurado
- Ícones do Desktop: Lixeira e Este Computador visíveis

### Apps removidos
| App | App |
|-----|-----|
| Teams | Cortana |
| Copilot | OneDrive |
| Clipchamp | Office Hub |
| OneNote | Outlook |
| Skype | Solitaire |
| Maps | News |
| Weather | To Do |
| Feedback Hub | Get Help |
| Power Automate | Mixed Reality |
| Dev Home | Family |
| Quick Assist | Steps Recorder |
| Snipping Tool | WordPad |
| Notepad (built-in) | Paint 3D |

---

## 📜 Scripts incluídos

| Script | Função |
|--------|--------|
| `Specialize.ps1` | Configurações do sistema durante instalação |
| `DefaultUser.ps1` | Configurações aplicadas a todos os usuários |
| `FirstLogon.ps1` | Executa no primeiro login |
| `UserOnce.ps1` | Configurações finais do usuário |
| `RemovePackages.ps1` | Remove AppX packages indesejados |
| `RemoveCapabilities.ps1` | Remove capabilities do Windows |
| `RemoveFeatures.ps1` | Desativa features opcionais |
| `MakeEdgeUninstallable.ps1` | Permite desinstalar o Edge |
| `SetStartPins.ps1` | Limpa o menu iniciar |

---

## ⚙️ Gerado com

- [schneegans.de/windows/unattend-generator](https://schneegans.de/windows/unattend-generator/) como base
- Customizações e scripts offline adicionados manualmente

---

## 📋 Requisitos

- Windows 10 ou Windows 11 (qualquer edição)
- Arquitetura: x64 (amd64)
- Pendrive com no mínimo 8GB

---

## 📄 Licença

MIT — pode usar, modificar e distribuir à vontade.
