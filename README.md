# Reconstructing-Urban-Mobility-Disruptions-from-Archival-Web-Data
This notebook reconstructs where and when mobility disruptions likely occurred during the San Francisco Dec 20–21, 2025 power outage using archival web content rather than real-time sensor feeds.
It automatically gathers news articles and user-provided links, extracts relevant text, detects location references specific to San Francisco, assigns a confidence score to each location mention, and converts them into geocoded point features. To improve credibility and interpretability, reconstructed points are spatially evaluated against static urban infrastructure (traffic signals) and a manually digitized outage footprint created directly within the notebook. The workflow produces journal-ready figures, summary statistics, and analysis-ready CSV/GeoJSON outputs suitable for academic or applied mobility research.

🔄 Workflow Summary (High Level)

> Collects archival sources using GDELT, manual URLs, and optional social media exports
> Extracts article/post text using trafilatura
> Identifies SF-specific locations (intersections, addresses, landmarks) using NLP + regex
> Assigns confidence tiers based on location specificity
> Geocodes locations with Nominatim (cached for reproducibility)
> Digitizes an outage footprint polygon in-notebook
> Validates reconstructed points against traffic signal infrastructure
> Generates maps, timelines, distance statistics, and tables
> Exports datasets for supplementary material or reuse

Key Outputs
> Figure 1: Study area map (digitized outage footprint + traffic signals + reconstructed points)
> Figure 2: Hotspots map (hexbin density of mentions; optional / density-dependent)
> Figure 3A–3B: High-confidence map + nearest-signal distance distribution
> Figure 4: Hourly timeline of high-confidence mentions
> Table 1: Summary metrics (overall + high-confidence subset)
> Exports: reconstructed_mentions.csv, reconstructed_mentions.geojson, outage_footprint.geojson, and raw source table

Data Inputs
> GDELT news search (no API key required)
> Manual URLs (you paste links)
> Optional social platform export CSV
> Optional seed CSV of links/posts

Intended Use Cases
> Historical reconstruction of mobility disruptions
> Validation of crowd-sourced or media-reported incidents
> Rapid exploratory analysis when official sensor data is unavailable
> Supplementary material for short-format journals or technical notes

🧩 Suggested Repository Name (Final Recommendation)
sf-blackout-mobility-reconstruction
Alternatives
urban-mobility-disruption-reconstruction

ai-assisted-outage-mapping

archival-mobility-disruption-analysis
