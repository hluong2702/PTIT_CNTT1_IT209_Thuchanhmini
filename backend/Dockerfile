FROM eclipse-temurin:21-jre-alpine

WORKDIR /app

# Tạo non-root user để tăng tính bảo mật
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Copy file jar đã build bằng Gradle
COPY build/libs/*.jar app.jar

# Phân quyền cho appuser
RUN chown appuser:appgroup app.jar

USER appuser

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
