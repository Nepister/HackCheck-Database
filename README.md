# HackCheck Database

Base Master de EFI para o HackCheck Engine 2.

## Estrutura

- `Bases/EFI-BASE.zip` — banco principal de Intel modernas e plataformas HEDT.
- `Bases/EFI-BASE2.zip` — banco de Intel antigas, Desktop/Mobile e AMD.
- `manifest.json` — versão, integridade e metadados dos pacotes.
- `catalog.json` — catálogo lógico das famílias de hardware conhecidas.

## Distribuição

Este repositório é público para permitir que o HackCheck Engine 2 obtenha a Base Master diretamente por HTTPS, sem exigir Git, Git LFS, GitHub Desktop ou login do usuário no GitHub.

O Engine consulta `manifest.json`, baixa os pacotes grandes pelo transporte HTTPS público do GitHub/LFS, valida tamanho e SHA-256 e mantém os arquivos no cache local para reutilização offline.

## Regra de uso

O HackCheck não deve copiar uma EFI inteira cegamente. As Bases são referências para seleção de componentes, configuração e comparação.

A seleção deve considerar fabricante, geração, arquitetura, plataforma (Notebook/Desktop/HEDT), socket/chipset quando houver evidência e características do hardware detectado.

Ivy Bridge e Ivy Bridge-E são tratados como plataformas diferentes: Ivy Bridge normal/Desktop/Mobile pertence ao banco `EFI-BASE2`, enquanto Ivy Bridge-E/X79 pertence ao banco `EFI-BASE`.

## Integridade

Os arquivos grandes são armazenados com Git LFS. Os SHA-256 dos objetos LFS estão registrados em `manifest.json` e são usados pelo HackCheck para validar os downloads HTTPS.
