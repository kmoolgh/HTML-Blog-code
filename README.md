# HTML-Blog-code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced Blog with Bootstrap</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <link rel="stylesheet" href="styles.css">
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    <script src="script.js" defer></script>
</head>
<body>
    <header class="navbar navbar-expand-lg navbar-dark bg-dark">
        <a class="navbar-brand" href="#">Advanced Blog</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav ml-auto">
                <li class="nav-item"><a class="nav-link" href="#about">About</a></li>
                <li class="nav-item"><a class="nav-link" href="#projects">Projects</a></li>
                <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
            </ul>
        </div>
    </header>
    <main class="container mt-4">
        <section id="about" class="mb-4">
            <h2>About Me</h2>
            <p>I am a web developer passionate about coding and designing websites.</p>
        </section>
        <section id="projects" class="mb-4">
            <h2>Projects</h2>
            <div class="card-deck">
                <div class="card">
                    <div class="card-body">
                        <h3 class="card-title">Project 1</h3>
                        <p class="card-text">Description of project 1.</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-body">
                        <h3 class="card-title">Project 2</h3>
                        <p class="card-text">Description of project 2.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>
    <footer class="bg-dark text-white mt-4 p-4 text-center">
        <h2>Leave a Comment</h2>
        <form id="comment-form" class="mb-4">
            <div class="form-group">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" class="form-control" required>
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" class="form-control" required>
            </div>
            <div class="form-group">
                <label for="comment">Comment:</label>
                <textarea id="comment" name="comment" class="form-control" required></textarea>
            </div>
            <button type="submit" class="btn btn-primary">Post Comment</button>
        </form>
        <div id="comments-section">
            <!-- Comments will be dynamically loaded here -->
        </div>
        <p>Contact me: your-email@example.com</p>
    </footer>
    <script>
        $(document).ready(function() {
            $('#comment-form').submit(function(e) {
                e.preventDefault();
                const comment = {
                    name: $('#name').val(),
                    email: $('#email').val(),
                    message: $('#comment').val(),
                    date: new Date().toLocaleString(),
                };
                displayComment(comment);
                $(this).trigger('reset');
            });

            function displayComment(comment) {
                $('#comments-section').append(`
                    <div class="comment border p-2 my-2">
                        <p><strong>${comment.name}</strong> (${comment.date})</p>
                        <p>${comment.message}</p>
                    </div>
                `);
            }
        });
    </script>
</body>
</html>
