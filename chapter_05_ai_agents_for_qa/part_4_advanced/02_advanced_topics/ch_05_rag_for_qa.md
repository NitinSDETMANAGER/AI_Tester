# RAG for QA

- **Author:** Nitin Choudhary
- **Role:** Sr SDET
.
- **LinkedIn:** https://www.linkedin.com/in/choudhary-nitin/

---

## 🎯 What is RAG?

**RAG (Retrieval-Augmented Generation)** enhances LLMs with external knowledge by retrieving relevant documents before generating responses.

---

## 📊 RAG for QA Use Cases

| Use Case | Knowledge Source |
|----------|------------------|
| Test case generation | Past test cases, requirements |
| Bug analysis | Historical bugs, solutions |
| Documentation Q&A | Test docs, wikis |
| Code review | Best practices, standards |

---

## 🛠️ Basic RAG Implementation

```python
from langchain.embeddings import OpenAIEmbeddings
from langchain.vectorstores import Chroma
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain.document_loaders import DirectoryLoader
from langchain_anthropic import ChatAnthropic
from langchain.chains import RetrievalQA

# 1. Load documents
loader = DirectoryLoader("./test_docs/", glob="**/*.md")
documents = loader.load()

# 2. Split into chunks
splitter = RecursiveCharacterTextSplitter(
    chunk_size=1000,
    chunk_overlap=200
)
chunks = splitter.split_documents(documents)

# 3. Create embeddings and store
embeddings = OpenAIEmbeddings()
vectorstore = Chroma.from_documents(
    documents=chunks,
    embedding=embeddings,
    persist_directory="./qa_knowledge_db"
)

# 4. Create retrieval chain
llm = ChatAnthropic(model="claude-3-5-sonnet-20241022")
qa_chain = RetrievalQA.from_chain_type(
    llm=llm,
    chain_type="stuff",
    retriever=vectorstore.as_retriever()
)

# 5. Query
result = qa_chain.invoke({
    "query": "How do we test the payment flow?"
})
print(result["result"])
```

---

## 🔧 QA Knowledge Base Example

### Index Structure

```
qa_knowledge/
├── test_standards/
│   ├── naming_conventions.md
│   ├── test_patterns.md
│   └── best_practices.md
├── past_test_cases/
│   ├── login_tests.md
│   ├── payment_tests.md
│   └── checkout_tests.md
├── bug_analysis/
│   ├── common_issues.md
│   └── solutions.md
└── requirements/
    ├── feature_specs.md
    └── acceptance_criteria.md
```

### Queries You Can Ask

- "Generate test cases similar to login tests"
- "What are common payment flow bugs?"
- "How should I name my test functions?"
- "What edge cases should I test for checkout?"

---

## 📚 See Also

- [Vector Databases](ch_05_vector_databases.md)
- [Memory Systems](ch_05_memory_systems.md)
