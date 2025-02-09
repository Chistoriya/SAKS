class AcademyAwards:
    def __init__(self):
        self.nominations = {}
    
    def nominate(self, actor, category, movie):
        if (actor, category) in self.nominations:
            print(f"Error: {actor} cannot be nominated twice in the '{category}' category.")
        else:
            self.nominations[(actor, category)] = movie
            print(f"{actor} nominated for '{category}' in '{movie}'")
    
    def show_nominations(self):
        print("\nCurrent Nominations:")
        for (actor, category), movie in self.nominations.items():
            print(f"{actor} - {category}: {movie}")

# Example Usage
oscars = AcademyAwards()
oscars.nominate("Actor A", "Best Actor", "Movie 1")
oscars.nominate("Actor A", "Best Actor", "Movie 2")  # This should trigger an error
oscars.nominate("Actor B", "Best Actor", "Movie 3")
oscars.nominate("Actor A", "Best Supporting Actor", "Movie 4")  # Allowed

oscars.show_nominations()
