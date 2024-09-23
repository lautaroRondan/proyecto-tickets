A continuación, te mostramos los scripts para crear las tablas `users` y `tickets`:
-- Tabla 'users'
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);

-- Tabla 'tickets'
CREATE TABLE tickets (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    name VARCHAR(255) NOT NULL,
    description TEXT,
    difficulty ENUM('fácil', 'medio', 'difícil') NOT NULL,
    gif_url VARCHAR(255),
    status ENUM('pendiente', 'completado') DEFAULT 'pendiente',
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE SET NULL
);
