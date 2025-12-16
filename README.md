# Smart Bike Telemetry System

A real-time bike telemetry monitoring application built with Flutter. This app connects to IoT sensors via MQTT to capture and display live ride data including speed, heart rate, and GPS location on an interactive map.

## Features

- **Live Dashboard**: Real-time display of current speed, heart rate (BPM), and G-force measurements
- **Interactive Map**: View your ride route in real-time using OpenStreetMap integration
- **Performance Charts**: Track speed and heart rate trends throughout your ride with interactive graphs
- **Ride Statistics**: View comprehensive summary data after completing a ride
- **MQTT Connectivity**: Connects to a bike telemetry sensor system via MQTT protocol for seamless data streaming
- **Dark Theme**: Modern dark UI optimized for outdoor use and battery efficiency

## Architecture

The app is structured around these key components:

- **MqttService**: Handles MQTT connections and telemetry data reception from the bike sensor
- **RideController**: Manages ride state and data persistence
- **Dashboard Page**: Main interface showing live telemetry data and map
- **Summary Page**: Post-ride analysis and statistics
- **Widgets**: Reusable components for maps, charts, and stats display

## Technologies

- **Framework**: Flutter (Dart)
- **Communication**: MQTT Client (mqtt_client: ^10.2.0)
- **Mapping**: Flutter Map with Latlong2
- **Charts**: FL Chart for performance visualization
- **Platforms**: Android, iOS, Web, Windows, macOS, Linux

## Getting Started

### Prerequisites

- Flutter SDK 3.10.3 or higher
- An active MQTT broker (currently configured for broker.hivemq.com)
- A bike telemetry sensor publishing to the "portenta/bike/json" topic

### Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   flutter pub get
   ```

3. Run the app:
   ```bash
   flutter run
   ```

## Project Structure

```
lib/
├── main.dart                 # App entry point
├── mqtt_service.dart         # MQTT connection and telemetry handling
├── ride_controller.dart      # Ride state management
├── pages/
│   ├── dashboard_page.dart   # Main dashboard with live data
│   ├── map_page.dart         # Full-screen map view
│   └── summary_page.dart     # Ride statistics and summary
└── widgets/
    ├── live_map.dart         # Reusable map widget
    ├── speed_hr_chart.dart   # Performance chart widget
    └── stats_cards.dart      # Statistics card widgets
```

## Configuration

The MQTT connection is configured with the following defaults:

- **Broker**: broker.hivemq.com
- **Port**: 1883 (TCP)
- **Topic**: portenta/bike/json
- **Keep-Alive**: 20 seconds

Modify these settings in `mqtt_service.dart` as needed for your telemetry system.

## Data Format

The app expects MQTT telemetry data in JSON format with the following fields:

```json
{
  "spd": 25.5,    // Speed in km/h
  "bpm": 145,     // Heart rate in beats per minute
  "g": 0.8,       // G-force measurement
  "lat": 40.7128, // Latitude
  "lng": -74.0060 // Longitude
}
```

## Future Enhancements

- GPS accuracy filtering and smoothing
- Elevation profile tracking
- Ride history and analytics
- Social sharing features
- Customizable alerts and notifications
- Offline data caching

## License

This project is open source and available under the MIT License.

## Support

For issues, feature requests, or questions, please create an issue in this repository.

---

**Built with Flutter** | Real-time Bike Telemetry Monitoring
