# Star Schema – Análise de Professores

Este projeto apresenta a modelagem dimensional (esquema estrela) para análise de dados de professores, com base em um diagrama relacional.

## 1. Fato_ProfessorCurso

Tabela fato que relaciona professor, cursos, disciplinas, departamentos e períodos de oferta.

### Colunas (chaves e métricas)
- **PK_Fato** (chave substituta)  
- **SK_Professor** (FK para Dim_Professor)  
- **SK_Curso** (FK para Dim_Curso)  
- **SK_Departamento** (FK para Dim_Departamento)  
- **SK_Disciplina** (FK para Dim_Disciplina)  
- **SK_Tempo** (FK para Dim_Tempo)  

### Medidas (fatos numéricos)
- **CargaHoraria_Ministrada**  
- **Quantidade_Disciplinas**  
- **Quantidade_Cursos**  
- **Quantidade_Departamentos** (quando houver múltipla vinculação)  

---

## 2. Dim_Professor

Informações descritivas do professor.

### Colunas
- **SK_Professor** (PK – chave substituta)  
- **ID_Professor** (chave natural do sistema transacional)  
- **Nome**  
- **Titulação** (Mestre, Doutor, etc.)  
- **Regime_Contratacao** (Integral, Parcial, Horista)  
- **Tempo_Carreira** (anos)  

---

## 3. Dim_Curso

Dados dos cursos ministrados.

### Colunas
- **SK_Curso** (PK)  
- **ID_Curso** (chave natural)  
- **Nome_Curso**  
- **Tipo_Curso** (Graduação, Pós, Extensão)  
- **Modalidade** (Presencial, EAD, Híbrido)  
- **Carga_Horaria_Total**  

---

## 4. Dim_Disciplina

Detalhes das disciplinas associadas aos cursos.

### Colunas
- **SK_Disciplina** (PK)  
- **ID_Disciplina** (chave natural)  
- **Nome_Disciplina**  
- **Área_Conhecimento**  
- **Créditos**  
- **Carga_Horaria**  

---

## 5. Dim_Departamento

Unidades acadêmicas responsáveis.

### Colunas
- **SK_Departamento** (PK)  
- **ID_Departamento** (chave natural)  
- **Nome_Departamento**  
- **Centro** (ex.: Ciências Exatas, Ciências Humanas)  

---

## 6. Dim_Tempo

Dimensão de datas, criada para análise temporal.

### Colunas
- **SK_Tempo** (PK)  
- **Data_Completa** (YYYY-MM-DD)  
- **Ano**  
- **Semestre**  
- **Trimestre**  
- **Mês**  
- **Nome_Mês**  
- **Dia_Semana**  
