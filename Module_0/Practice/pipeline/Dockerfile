FROM python:3.13.11-slim
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/

WORKDIR /code
COPY pyproject.toml .python-version uv.lock ./
RUN uv sync --locked
# Add virtual environment to PATH so we can use installed packages
ENV PATH="/code/.venv/bin:$PATH"


COPY pipeline.py . 

ENTRYPOINT ["python","pipeline.py"]