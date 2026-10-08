# Project-3-ABC-Backend
1. Ensure you create the .env file with your Pooled connection link
 ```
DATABASE_URL=postgresql://postgres.c...
 ```

2. Ensure you have a Supabse project created with the details
```
CREATE TABLE IF NOT EXISTS abc_users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(150) NOT NULL UNIQUE,
    password VARCHAR(150) NOT NULL
);

CREATE TABLE IF NOT EXISTS abc_posts (
    id SERIAL PRIMARY KEY,
    title TEXT,
    content TEXT,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);
ALTER TABLE posts
    ADD COLUMN user_id INT,
    ADD CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(id);
INSERT INTO abc_users (username, password)
VALUES
    ('john123', 'password123'),
    ('sarah456', 'password456'),
    ('mike789', 'password789');

INSERT INTO abc_posts (title, content)
VALUES
    ('My First Post', 'This is my first post.'),
    ('Learning PostgreSQL', 'I am learning how to work with PostgreSQL databases.'),
    ('My New Project', 'I just built a new project using Node.js and Express.');

```
