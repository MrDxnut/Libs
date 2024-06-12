Инструкция запуска проекта

1) Запустите PostgreSQL.
2) Создайте необходимые таблицы:
CREATE TABLE book (
    id BIGINT PRIMARY KEY,
    isbn VARCHAR(255) NOT NULL,
    title VARCHAR(255) NOT NULL,
    genre VARCHAR(255),
    description TEXT,
    author VARCHAR(255) NOT NULL
);

CREATE TABLE library_record (
    id BIGSERIAL PRIMARY KEY,
    book_id BIGINT NOT NULL,
    borrowed_at TIMESTAMP NOT NULL,
    due_at TIMESTAMP,
    returned_at TIMESTAMP,
    FOREIGN KEY (book_id) REFERENCES book(id)
);

Запуск приложения:
Запустите с помощью Maven: mvn spring-boot:run

Использование Swagger UI: http://localhost:8080/swagger-ui.html
