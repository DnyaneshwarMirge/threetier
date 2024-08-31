# Use an official Golang runtime as a parent image
FROM golang:1.19

# Set the working directory in the container
WORKDIR /app

# Copy the Go source code
COPY . .

# Install the Go dependencies (if any)
RUN go mod tidy

# Set environment variables
ENV DB_HOST=db
ENV DB_USER=test
ENV DB_PASSWORD=1234
ENV DB_NAME=employees
ENV DB_PORT=5432
ENV ALLOWED_ORIGINS=http://frontend:3000

# Build the Go app
RUN go build -o main .

# Expose the port the app runs on
EXPOSE 8080

# Run the Go app
CMD ["./main"]
