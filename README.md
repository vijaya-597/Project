Here's a simple Python program that generates basic HTML code based on user input:

HTML Code Generator
*Program Description*
This program generates basic HTML code for common elements like headings, paragraphs, links, images, and lists.

*Code*
```
def generate_html():
    print("HTML Code Generator")
    print("--------------------")

    while True:
        print("\nOptions:")
        print("1. Heading")
        print("2. Paragraph")
        print("3. Link")
        print("4. Image")
        print("5. List")
        print("6. Quit")

        choice = input("Choose an option: ")

        if choice == "1":
            heading_text = input("Enter heading text: ")
            heading_level = input("Enter heading level (1-6): ")
            print(f"<h{heading_level}>{heading_text}</h{heading_level}>")

        elif choice == "2":
            paragraph_text = input("Enter paragraph text: ")
            print(f"<p>{paragraph_text}</p>")

        elif choice == "3":
            link_text = input("Enter link text: ")
            link_url = input("Enter link URL: ")
            print(f"<a href='{link_url}'>{link_text}</a>")

        elif choice == "4":
            image_url = input("Enter image URL: ")
            image_alt = input("Enter image alt text: ")
            print(f"<img src='{image_url}' alt='{image_alt}'>")

        elif choice == "5":
            list_items = input("Enter list items (comma-separated): ")
            list_items = list_items.split(",")
            list_html = "<ul>\n"
            for item in list_items:
                list_html += f"<li>{item.strip()}</li>\n"
            list_html += "</ul>"
            print(list_html)

        elif choice == "6":
            break

        else:
            print("Invalid option. Please choose again.")

if __name__ == "__main__":
    generate_html()
```

*Example Usage*
1. Run the program.
2. Choose an option (e.g., 1 for heading).
3. Enter the required information (e.g., heading text and level).
4. The program will generate and print the corresponding HTML code.

This program provides a simple way to generate basic HTML code for common elements. You can modify and extend it to suit your needs.
