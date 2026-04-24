# port-scanner
import socket
from datetime import datetime

# ─────────────────────────────────────
# STEP 1: Set the target and port range
# Change target to any IP or website
# ─────────────────────────────────────
target = "127.0.0.1"   # localhost (your own PC) - safe to test!
start_port = 1
end_port   = 1024


# ─────────────────────────────────────
# STEP 2: Function to scan one port
# Returns True if port is open
# Returns False if port is closed
# ─────────────────────────────────────
def scan_port(ip, port):
    try:
        # Create a socket connection
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(0.5)  # Wait max 0.5 seconds

        # Try to connect to the port
        result = sock.connect_ex((ip, port))
        sock.close()

        # result == 0 means port is OPEN
        if result == 0:
            return True
        else:
            return False

    except:
        return False


# ─────────────────────────────────────
# STEP 3: Main scan function
# Loops through all ports and checks each one
# ─────────────────────────────────────
def run_scanner():
    print("=" * 45)
    print("       PORT SCANNER - Cyber Security Tool")
    print("=" * 45)
    print(f"Target   : {target}")
    print(f"Ports    : {start_port} to {end_port}")
    print(f"Started  : {datetime.now().strftime('%Y-%m-%d %H:%M:%S')}")
    print("-" * 45)

    open_ports = []  # List to store open ports

    # Loop through every port number
    for port in range(start_port, end_port + 1):

        # Show progress every 100 ports
        if port % 100 == 0:
            print(f"Scanning port {port}...")

        # Check if port is open
        if scan_port(target, port):
            print(f"  [OPEN]  Port {port}")
            open_ports.append(port)

    # Summary
    print("-" * 45)
    print(f"Scan Complete!")
    print(f"Open Ports Found : {len(open_ports)}")
    if open_ports:
        print(f"Open Ports List  : {open_ports}")
    print("=" * 45)


# ─────────────────────────────────────
# STEP 4: Run the scanner
# ─────────────────────────────────────
run_scanner()
Python TCP port scanner for cyber security
