# 🩺 TOMMUS Image System: Auditoria Técnica e Relatório Profissional

**Data:** 11 de Março de 2026  
**Status:** Desenvolvimento Ativo (v0.0.6)  
**Líder do Projeto:** Raquel Pantojo  

---

## 1. Resumo Executivo
O **TOMMUS Image System** é uma interface de processamento de imagens médicas de alta precisão desenvolvida em C# (WPF) para diagnósticos de ultrassom em tempo real. O sistema integra SDKs complexos de hardware (Telemed) com uma interface de usuário moderna, facilitando o diagnóstico em phantoms de mama e o controle de tomografia.

Este relatório serve como uma auditoria profissional para a transição de uma fase de "integração/testes" para uma arquitetura de "produto escalável".

---

## 2. Arquitetura Técnica

### 🛠️ Stack Tecnológica
- **Framework:** .NET Framework 4.7.2 / WPF (Windows Presentation Foundation)
- **Linguagem:** C#
- **Integração de Hardware:** `Usgfw2Lib` baseada em COM (Telemed SDK)
- **Controle de Periféricos:** Comunicação Serial (ESP32 para controle de motor/tomografia)
- **Gráficos:** Renderização mista WinForms/WPF (WindowsFormsHost para DirectShow)

### 🏗️ Interação entre Componentes
- **Camada de UI:** XAML com `GlobalStyles.xaml` para consistência visual (Fontes Poppins & Extenda). Uso de `MainViewModel.cs` para vinculação de dados (MVVM parcial).
- **Serviços:** `StatusService.cs` para gestão centralizada de notificações na StatusBar.
- **Hardware:** `MainWindow.xaml.cs` gere o ciclo de vida dos objetos COM (`IProbe`, `IUsgDataView`, etc.) e comunicação serial com ESP32.
- **Lógica de Janelas:** `DopplerWindowManager.cs` para gestão de janelas auxiliares para modos avançados.

---

## 3. Progresso e Marcos de Desenvolvimento

| Funcionalidade | Status | Maturidade Profissional |
| :--- | :--- | :--- |
| **Scan Modo B** | ✅ Funcional | Alta (Estável) |
| **Controles TGC/Ganho** | ✅ Implementado | Alta (Sliders e Gráficos) |
| **Gestão de Pacientes** | ✅ Funcional | Média (JSON, Folder structure) |
| **Tomografia (Motor)** | ✅ Funcional | Alta (Linear, Vertical e Rotacional) |
| **Modo Cine (Vídeo)** | ✅ Funcional | Média (Aguardando Otimização) |
| **Ângulo/Foco** | ✅ Implementado | Média (Steering Angle & Focal Depth) |
| **Modo Doppler** | 🔄 Em Progresso | Baixa (Alpha - Integração de Janelas) |
| **Localização (Idioma)** | 🔄 Em Progresso | Implementação via `Resources.resx` |

---

## 4. Auditoria de Qualidade e Insights Técnicos

### ✅ Pontos Fortes
- **Integração Robusta de SDK:** Excelente domínio da interface `Usgfw2Lib`.
- **Consistência de Marca:** O uso de estilos centralizados e tipografia customizada eleva a percepção profissional.
- **Performance em Tempo Real:** Manipulação eficiente de dados de alta frequência e callbacks de RF.

### ⚠️ Riscos e Débito Técnico
- **Padrão "God Object":** O arquivo `MainWindow.xaml.cs` (5000+ linhas) permanece como o maior desafio de manutenção, concentrando lógica de hardware e UI.
- **Gestão de Recursos:** Ciclo de vida de objetos COM Telemed requer monitoramento rigoroso para evitar memory leaks.
- **Complexidade de UI:** A transição completa para MVVM é necessária para reduzir a dependência do code-behind e melhorar a testabilidade.

---

## 5. Roteiro Profissional (Melhorias a Implementar)

### � Etapa 1: Funcionalidades Pendentes (Prioridade Máxima)
- **Processamento de Sinal RF:** Implementação completa da lógica de gráficos RF (atualmente em Python) para o C#.
- **Exportação Modo Cine:** Implementar o salvamento de vídeos em formatos otimizados (ex: MP4/AVI) com metadados do paciente.
- **Controle Serial Avançado:** Finalizar a integração com o ESP32 para controle preciso de movimentação vertical, linear e rotacional.

### � Etapa 2: Reestruturação Arquitetural
- **Migração para MVVM:** Desacoplar a lógica de hardware da UI usando `ViewModels`.
- **Abstração de Hardware:** Criar um `ScannerService` para encapsular chamadas do Telemed, permitindo testes unitários.

### � Etapa 3: Dados e Escalabilidade
- **Banco de Dados:** Migrar o armazenamento de pacientes de arquivos `.txt` para SQLite ou SQL Server (conformidade com padrões médicos).
- **Sistema de Logs Profissional:** Implementar um log de sistema para diagnóstico de erros em campo.

---

> [!NOTE]
> Este relatório reflete o estado atual do desenvolvimento. A refatoração para MVVM é o passo arquitetural mais importante para a profissionalização do software.
