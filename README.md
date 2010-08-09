![ISBN](http://upload.wikimedia.org/wikipedia/commons/thumb/2/28/EAN-13-ISBN-13.svg/540px-EAN-13-ISBN-13.svg.png)

Bookland provides a simple ISBN class in Ruby.

    >> book = Bookland::ISBN.new("0262011530")
    >> book.to_isbn13
    => "9780262011532"
    >> book.to_s(1, 3, 5)
    => "0-262-01153-0"
    >> ISBN.new("9780262011532") == book
    => true
    >> invalid_book = ISBN.new("0262011531") # This is an invalid ISBN
    => false
    >> invalid_book.to_isbn13
    => Bookland::ISBNError: ISBN not valid

Conversely, use the class methods:

    >> Bookland::ISBN.to_13("0262011530")
    => "9780262011532"
    >> Bookland::ISBN.to_10("9780262011532")
    => "0262011530"

Specs pass against Ruby 1.8.7, REE, and Ruby 1.9.1.
