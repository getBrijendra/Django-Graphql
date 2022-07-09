Django and Graphql example.

pip install django graphene-django
django-admin startproject books_api
cd books_api
python manage.py startapp api
python manage.py makemigrations
python manage.py migrate
python manage.py loaddata data.json
python manage.py runserver

Sample Queries -

query {
allBooks {
id
title
author
yearPublished
review
}
}

query {
book(bookId: 2) {
id
title
author
}
}

mutation createMutation {
createBook(bookData: {title: "Things Apart", author: "Chinua Achebe", yearPublished: "1985", review: 3}) {
book {
title,
author,
yearPublished,
review
}
}
}

mutation updateMutation {
updateBook(bookData: {id: 6, title: "Things Fall Apart", author: "Chinua Achebe", yearPublished: "1958", review: 5}) {
book {
title,
author,
yearPublished,
review
}
}
}

mutation deleteMutation{
deleteBook(id: 6) {
book {
id
}
}
}
