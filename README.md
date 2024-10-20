school_coords = (40.712776, -74.005974)  # Replace with actual latitude and longitude

# Get your current location (use any method, like geopy)
def get_current_location():
    # Placeholder: Replace with actual code to get your current GPS location
    return (40.730610, -73.935242)  # Example: New York City

# Check if you're within a certain radius (in kilometers) of school
def near_school(current_coords, school_coords, radius_km=0.5):
    return geopy.distance.distance(current_coords, school_coords).km < radius_km

# Example command to connect/disconnect VPN
def toggle_vpn(turn_on):
    if turn_on:
        os.system("vpn-command connect")  # Replace with actual command to start VPN
    else:
        os.system("vpn-command disconnect")  # Replace with actual command to stop VPN

# Main logic
current_coords = get_current_location()

if near_school(current_coords, school_coords):
    print("You are near school. VPN is disabled.")
    toggle_vpn(False)
else:
    print("You are away from school. VPN is enabled.")
    toggle_vpn(True)
