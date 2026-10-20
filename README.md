# Lab 08 — NestJS dependency injection and DTO validation

Requires Node.js 22 or newer. From the project directory run `npm ci`, then `npm run start:dev`. The API prefix is `/api`; the default port is 3000. No credentials or external services are needed.

- `STORAGE=memory npm run start:dev`: seed an isolated memory store from data/courses.json. Default storage is file; file mode persists course changes to that JSON file.
- `LOG_TO_FILE=true STORAGE=memory npm run start:dev`: also write timestamped events to logs/app.log.
- `FEE_POLICY=standard STORAGE=memory npm run start:dev`: standard fees (default).
- `FEE_POLICY=merit STORAGE=memory npm run start:dev`: merit discounts at CGPA 3.0 and 3.5.
- `PORT=3001`: override the listening port.

Run `npm test`, `npm run test:e2e`, and `npm run build`. Start a fresh memory-mode server, then run `npm run test:postman` twice or import postman/Lab08_Tasks.postman_collection.json into Postman. Each complete run creates and deletes CS-420; avoid interrupting the run between these requests. The suite assumes the six-course seed and can run with either fee policy.

GET /api/students and GET /api/students/:rollNumber expose the Student foundation. Courses support list/search/filter/sort/limit, stats, lookup, POST, PUT, PATCH and DELETE. PUT requires every nonoptional field except code; PATCH accepts partial changes. The PDF describes a partial UpdateCourseDto but also says PUT requires all fields: a required ReplaceCourseDto resolves that distinction, while UpdateCourseDto follows the requested PartialType/OmitType expression.

The checkout was empty, so there was no earlier Student implementation or lab manual to preserve. Department values used here are Computer Science, Software Engineering and Data Science. Nest components were authored directly in the standard layout rather than generated with CLI commands.

See RESULTS.md and Lab08_Report.docx for captured validation evidence. Runner screenshots show Newman (the Postman command-line runner), not the Postman desktop UI. No GitHub publication is performed automatically.
