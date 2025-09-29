# 🎯 Pogo

[![npm version](https://img.shields.io/npm/v/pogo.svg)](https://www.npmjs.com/package/pogo)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.9%2B-blue.svg)](https://www.typescriptlang.org/)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-green.svg)](https://nodejs.org/)

A MongoDB-compatible API with SQLite backend for TypeScript applications.

## 📋 Overview

Pogo provides a familiar MongoDB-like interface for document-based operations while using SQLite as the underlying storage engine. This gives you the flexibility of document databases with the reliability and simplicity of SQLite.

## ✨ Features

- 🔄 MongoDB-compatible API for document operations
- 💾 SQLite backend for reliable local storage
- 🔍 Advanced query capabilities with `where()` filtering
- 📦 Collection-based data organization
- 🔐 Transaction support with `withTransaction()`
- ✅ Built-in validation utilities
- 🎨 Full TypeScript support
- 🧪 Comprehensive test coverage

## 📦 Installation

```bash
npm install pogo
```

## 🚀 Quick Start

```typescript
import { connect, collections, save, find } from 'pogo';

// Connect to database
await connect({ filepath: './data.db' });

// Save documents
await save(collections.users, { name: 'Alice', age: 30 });

// Query documents
const users = await find(collections.users, { age: { $gte: 25 } });

// Close connection
await close();
```

## 🔧 Requirements

- Node.js >= 18.0.0
- TypeScript >= 5.9.2

## 📚 Core API

### Connection Management

- `connect(config)` - Establish database connection
- `close()` - Close database connection
- `isConnected()` - Check connection status
- `withConnection(fn)` - Execute function with connection
- `withTransaction(fn)` - Execute function in transaction
- `getDatabaseStats()` - Get database statistics
- `maintenance()` - Run database maintenance

### Document Operations

- `save(collection, document)` - Save single document
- `saveMany(collection, documents)` - Save multiple documents
- `find(collection, filter)` - Find documents matching filter
- `findOne(collection, filter)` - Find single document
- `get(collection, id)` - Get document by ID
- `updateMany(collection, filter, update)` - Update multiple documents
- `deleteOne(collection, filter)` - Delete single document
- `deleteMany(collection, filter)` - Delete multiple documents

### Query Utilities

- `where(filter)` - Build advanced queries
- `raw(sql, params)` - Execute raw SQL

### Validation

- `isUnique(collection, field, value)` - Check field uniqueness

### Collections

- `Collection` - Base class for type-safe collections

## 🧪 Development

```bash
# Run tests
npm test

# Build project
npm run build

# Run example
npm run example
```

## 📄 License

MIT

## 🤝 Contributing

Issues and pull requests are welcome.