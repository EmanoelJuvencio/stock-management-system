# 📦 Sistema de Gerenciamento de Estoque

Este sistema permite o rastreamento eficiente de produtos, monitoramento de estoque, geração de alertas e integração com fornecedores para otimizar a reposição de mercadorias.

## 🏛️ Entidades

### **1. Produto**
Representa um item armazenado no estoque.
- `id` (string) - Identificação única do produto
- `name` (string) - Nome do produto
- `stock_quantity` (number) - Quantidade disponível no estoque
- `minimum_quantity` (number) - Quantidade mínima recomendada
- `size` (string) - Tamanho do produto (opcional)
- `color` (string) - Cor do produto (opcional)
- `unit_price` (number) - Preço unitário do produto

### **2. Venda**
Registra a saída de produtos do estoque.
- `id` (string) - Identificação única da venda
- `products` (array de Produto) - Lista de produtos vendidos
- `quantity` (number) - Quantidade total de produtos vendidos
- `date` (date) - Data da venda
- `total_price` (number) - Valor total da venda

### **3. Estoque**
Gerencia a movimentação dos produtos.
- `products` (array de Produto) - Produtos disponíveis no estoque
- `transactions` (array de Transaction) - Histórico de entradas e saídas do estoque

### **4. Movimentação**
Registra mudanças no estoque.
- `id` (string) - Identificação única da movimentação
- `product` (Produto) - Produto envolvido
- `type` (string) - Tipo da movimentação (`entry` ou `exit`)
- `quantity` (number) - Quantidade movimentada
- `date` (date) - Data da movimentação

### **5. Alerta**
Notifica quando o estoque atinge o nível mínimo.
- `id` (string) - Identificação única do alerta
- `product` (Produto) - Produto associado
- `type` (string) - Tipo do alerta (`low_stock`, `restock_needed`)
- `channel` (string) - Canal de envio (`email`, `system_notification`)
- `status` (string) - Status do alerta (`pending`, `resolved`)

### **6. Ordem de Compra**
Automatiza pedidos para reabastecimento.
- `id` (string) - Identificação única da ordem
- `products` (array de Produto) - Produtos solicitados
- `total_quantity` (number) - Quantidade total solicitada
- `status` (string) - Status da ordem (`pending`, `sent`, `received`)
- `supplier` (Supplier) - Fornecedor responsável

### **7. Fornecedor**
Representa fornecedores dos produtos.
- `id` (string) - Identificação única do fornecedor
- `name` (string) - Nome da empresa fornecedora
- `contact` (string) - Informações de contato
- `delivery_time` (number) - Prazo médio de entrega em dias

---

## ⚡ Casos de Uso

### ✅ **Gerenciar Produtos**
- Criar, editar e excluir produtos
- Definir atributos (tamanho, cor, preço)
- Atualizar estoque manualmente

### 📊 **Rastreamento de Estoque**
- Consultar status em tempo real
- Registrar movimentações de entrada e saída

### 🚨 **Definir e Monitorar Quantidades Mínimas**
- Configurar limites mínimos por produto
- Gerar alertas quando o estoque atingir o mínimo

### 🔔 **Gerenciar Alertas**
- Enviar notificações por e-mail e sistema
- Listar e visualizar alertas pendentes

### 📈 **Registrar e Consultar Histórico de Vendas**
- Visualizar vendas por período
- Calcular lucro por produto
- Identificar produtos mais vendidos

### 📉 **Analisar Tendências de Estoque**
- Gerar relatórios de consumo e reposição
- Sugerir compras com base no histórico de vendas

### 🛒 **Gerenciar Ordens de Compra**
- Criar ordens de compra automaticamente
- Enviar pedidos para fornecedores
- Atualizar status das ordens

### 🔗 **Integrar com Fornecedores**
- Receber atualizações sobre prazos de entrega
- Sincronizar pedidos e confirmações

---
