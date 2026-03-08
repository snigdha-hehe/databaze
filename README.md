# Travel Planner and budget estimator
## DlightPlanner / Voya – Smart Travel Itinerary Planner

DlightPlanner (branded in the UI as **Voya**) is a desktop travel-planning application built with Java Swing. It helps users plan trips by combining flights, hotels, tourist spots, and cost estimates into a smart, guided itinerary flow.

### What this project does

- **Welcome & quiz flow**: Starts with an animated `VoyaWelcome` screen and a quiz to understand user preferences.
- **Smart itinerary builder**: Guides the user through cities, flights, hotels, and multi‑city options to build an itinerary.
- **Rich travel data**: Uses JSON resources for cities, airports, hotels, tourist spots, and local costs.
- **Cost & weather awareness**: Services estimate local costs and fetch contextual data (e.g. weather) to refine suggestions.
- **Export & utilities**: Utility classes support database connections, file handling, theming, and PDF generation for summaries.

### Tech stack & main components

- **Language & UI**: Java (Swing) desktop application.
- **Core packages**:
  - `com.dlightplanner.gui`: All screens (welcome, quiz, home, itinerary, flights, hotels, multi‑city flow, booking summary, etc.).
  - `com.dlightplanner.models`: Domain models such as `City`, `Airport`, `Flight`, `Hotel`, `TouristSpot`, and request objects.
  - `com.dlightplanner.services`: Business logic for cities, airports, flights, hotels, weather, costs, tourist spots, and itinerary generation.
  - `com.dlightplanner.repository`: Data access components (e.g. `CityRepository`).
  - `com.dlightplanner.utils`: Shared utilities like `DBConnection`, `FileUtils`, `Theme`, and `PDFGenerator`.
- **Data files** (in `resources/`): `cities.json`, `airports.json`, `hotels.json`, `tourist_spots.json`, `local_costs.json`.

### How the app works (high level flow)

1. **Entry point**: `VoyaWelcome` (in `com.dlightplanner.gui`) is the main class with `public static void main`, launching a full‑screen animated welcome screen.
2. **On continue**: The user is taken to `QuizPage`, which gathers preferences to tailor suggested destinations and itineraries.
3. **Planning screens**: The user navigates through pages like `HomePage`, `CityDetailPage`, `FlightPage`, `HotelPage`, `MultiCityItineraryPage`, and `BookingSummaryPage`.
4. **Services & data**: GUI pages call services in `com.dlightplanner.services` and repositories in `com.dlightplanner.repository` to load and compute data from JSON resources and (optionally) a database via `DBConnection`.
5. **Output**: A complete itinerary with flights, hotels, tourist spots, and cost estimates is shown, and can be summarized/exported (e.g. via `PDFGenerator`).

### Getting started

**Prerequisites**

- Java Development Kit (JDK) 17 or later.
- A Java‑capable IDE (IntelliJ IDEA, Eclipse, VS Code with Java) is recommended.

**Run from an IDE**

1. Open the project in your IDE.
2. Mark `dlightplanner/src` as a source root if needed.
3. Run the `main` method in `com.dlightplanner.gui.VoyaWelcome`.

**Run from the command line (basic setup)**

From the project root:

```bash
javac -d out -cp dlightplanner/src dlightplanner/src/com/dlightplanner/gui/VoyaWelcome.java
java -cp out com.dlightplanner.gui.VoyaWelcome
```

You may need to compile additional classes or configure your classpath depending on your environment; using an IDE is usually simpler.



