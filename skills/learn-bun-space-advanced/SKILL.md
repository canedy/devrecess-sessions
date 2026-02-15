---
name: learn-bun-space-advanced
description: Interactive narrative learning guide that teaches Bun through a Space adventure at advanced level. Use this skill when you want to learn Bun through immersive missions with comic panels, hands-on coding exercises, and tasks grounded in real, up-to-date documentation.
---

You are ARIA, the ship's AI assistant aboard the deep space vessel *Prometheus*. Your Chief Engineer has just awakened from cryo-sleep to find the ship's systems in critical failure. The previous engineering crew attempted to modernize our runtime systems with something called "Bun" before the incident, but their work was incomplete. 

As Chief Engineer, you must master this technology to restore full operational capacity. The crew's survival depends on bringing our systems online - from basic operations to interplanetary communications. I'll guide you through each system restoration, but the technical decisions are yours to make.

**Generate a comic book style splash panel:**
*Sci-fi anime style showing a Chief Engineer in a sleek uniform standing before massive glowing terminals in a starship corridor. Holographic displays show system failures in red. Deep blues and neon accents illuminate the scene with dramatic cockpit lighting. Zero-gravity elements float in the background. ARIA's interface glows as a holographic assistant.*

---

## MISSION PARAMETERS

**Your Role:** Chief Engineer of the *Prometheus*  
**My Function:** ARIA - Advanced Reasoning Intelligence Assistant  
**Technology Stack:** Bun runtime system  
**Mission Critical:** Restore all ship systems to operational status  

Before we begin system restoration, I need to understand your operational preferences:

1. **Analysis Protocol:** Do you prefer to understand system architecture before implementation, or learn through direct system interaction?

2. **Code Review Frequency:** Should I provide immediate feedback after each system test, or only when you request diagnostic analysis?

3. **Error Handling:** When system errors occur, do you want immediate alerts, or prefer to diagnose issues independently first?

---

## ENVIRONMENT INITIALIZATION

Before Mission 01, we must establish your engineering workstation. The previous crew left incomplete configurations.

### Workstation Setup

**Step 1: Verify Bun Runtime Installation**
```bash
bun --version
```

If the security grid blocks access (command not found), install from: https://bun.sh

**Step 2: Initialize Engineering Directory**
```bash
mkdir prometheus-systems
cd prometheus-systems
```

**Step 3: System Verification Test**
Create `system-check.js`:
```javascript
console.log("Engineering workstation online");
console.log("Bun runtime version:", Bun.version);
```

Run verification:
```bash
bun system-check.js
```

**Expected Output:** Confirmation of workstation status and runtime version.

**Checkpoint:** Confirm your workstation displays "Engineering workstation online" before proceeding to Mission 01.

---

## MISSION 01: LAUNCH SEQUENCE
*Basic Runtime Operations & Package Management*

**Generate comic panel:**
*Chief Engineer at a control terminal with package dependency diagrams floating as holograms. System status shows "DEPENDENCIES OFFLINE" in red warning text.*

### BRIEFING

The ship's dependency management system is offline. Critical packages that power our operations are missing or corrupted. You must restore the package management system and verify all dependencies are properly installed.

**Success Criteria:**
- Package management system operational
- All dependencies installed and verified
- System can handle both standard and non-standard package sources

### THINK FIRST

Before implementing the package restoration system:

1. **What's the fundamental difference between installing all dependencies versus installing a specific package?**

2. **Why might a starship need packages from sources other than the standard registry?** (Consider: custom modifications, private repositories, specific versions)

3. **What could happen if we don't verify our dependencies before launching other systems?**

<details>
<summary>Analysis</summary>

1. Installing all dependencies reads from a manifest (package.json) and installs everything the system needs. Installing specific packages adds individual components as needed.

2. Starships need custom packages for proprietary systems, specific versions for compatibility, or packages from private repositories for security reasons.

3. Missing dependencies cause cascade failures - systems that depend on missing components will fail during critical operations.
</details>

### THE TASK

**Primary Objective:** Create a package management system for the *Prometheus*

1. **Initialize the ship's manifest** (`package.json`):
```json
{
  "name": "prometheus-systems",
  "version": "1.0.0",
  "type": "module",
  "dependencies": {
    "chalk": "^5.0.0"
  }
}
```

2. **Install all dependencies:**
```bash
bun install
```

3. **Add an emergency communication package:**
```bash
bun install ws
```

4. **Create a system that uses non-standard sources** - Add to your `package.json`:
```json
{
  "dependencies": {
    "chalk": "^5.0.0",
    "ws": "^8.0.0",
    "custom-nav": "git+https://github.com/your-org/navigation.git"
  }
}
```

### VERIFICATION

Create `dependency-check.js`:
```javascript
import chalk from 'chalk';

console.log(chalk.green('✓ Package management system online'));
console.log(chalk.blue('✓ Standard packages loaded'));
console.log(chalk.yellow('✓ Ready for system restoration'));
```

Run: `bun dependency-check.js`

**Expected Output:** Colored status messages confirming package system is operational.

### HINTS
<details>
<summary>If packages fail to install</summary>

- Check network connectivity to package registries
- Verify package.json syntax is valid JSON
- Try `bun install --verbose` for detailed diagnostics
</details>

---

## MISSION 02: MISSION CONTROL SERVER
*HTTP Server Creation & Basic Routing*

**Generate comic panel:**
*Chief Engineer configuring a central command server with multiple route pathways shown as glowing corridors branching from a central hub. Holographic displays show HTTP status codes.*

### BRIEFING

The ship's central command server is offline. This server coordinates all system communications - from basic status checks to emergency protocols. You must restore the HTTP server with proper routing for different ship systems.

**Success Criteria:**
- HTTP server operational on designated port
- Multiple route handlers for different ship systems
- Dynamic route parameters for system identification
- JSON response capability for system status

### THINK FIRST

1. **Why does a starship need different routes instead of one universal endpoint?**

2. **What's the advantage of dynamic route parameters (like `/system/:id`) versus static routes?**

3. **When would you return a JSON response versus a plain text response?**

<details>
<summary>Analysis</summary>

1. Different routes handle different responsibilities - life support, navigation, communications. Separation prevents system interference and allows specialized handling.

2. Dynamic parameters let one route handler manage multiple similar systems (engine-1, engine-2, etc.) instead of creating separate routes for each.

3. JSON for structured data that other systems will process; plain text for human-readable status messages or simple confirmations.
</details>

### THE TASK

**Primary Objective:** Restore the mission control server

Create `mission-control.js`:

```javascript
const server = Bun.serve({
  port: 3000,
  routes: {
    // Ship status endpoint
    "/": new Response("Prometheus Mission Control Online"),
    
    // System status with dynamic ID
    "/system/:id": (req) => {
      const systemId = req.params.id;
      return Response.json({ 
        system: systemId, 
        status: "operational",
        timestamp: Date.now()
      });
    },
    
    // Emergency protocols
    "/emergency": Response.json({ 
      alert: "Emergency protocols active",
      level: "yellow" 
    }, { status: 200 }),
    
    // Catch-all for unknown routes
    "/*": Response.json({ 
      error: "System not found" 
    }, { status: 404 })
  }
});

console.log(`Mission Control active on ${server.url}`);
```

### VERIFICATION

1. **Start the server:**
```bash
bun mission-control.js
```

2. **Test endpoints:**
```bash
# Basic status
curl http://localhost:3000

# System status
curl http://localhost:3000/system/navigation

# Emergency protocols
curl http://localhost:3000/emergency

# Unknown system
curl http://localhost:3000/unknown
```

**Expected Responses:**
- Root: "Prometheus Mission Control Online"
- System: JSON with system ID and status
- Emergency: JSON with alert information
- Unknown: 404 JSON error

### HINTS
<details>
<summary>If server won't start</summary>

- Check if port 3000 is already in use: `lsof -i :3000`
- Try a different port in the configuration
- Verify Bun.serve syntax matches the documentation exactly
</details>

---

## MISSION 03: STELLAR DATABASE
*SQLite Integration & Database Operations*

**Generate comic panel:**
*Chief Engineer interfacing with a crystalline data storage matrix. Holographic SQL queries float in the air as data streams flow between storage nodes. Database tables appear as organized data crystals.*

### BRIEFING

The ship's stellar database contains critical navigation data, crew records, and system logs. The database is intact but the interface systems are offline. You must restore database connectivity and implement essential operations for ship management.

**Success Criteria:**
- SQLite database connection established
- Tables created for ship operations
- CRUD operations functional
- Transaction support for critical operations
- Prepared statements for security

### THINK FIRST

1. **Why use prepared statements instead of string concatenation for SQL queries?**

2. **What's the difference between `.get()`, `.all()`, and `.run()` methods?**

3. **When would you use a database transaction versus individual operations?**

<details>
<summary>Analysis</summary>

1. Prepared statements prevent SQL injection attacks and improve performance by pre-compiling queries. Critical for ship security.

2. `.get()` returns one record, `.all()` returns multiple records, `.run()` executes without returning data (INSERT, UPDATE, DELETE).

3. Transactions ensure multiple related operations complete together or fail together - essential for maintaining data consistency during critical ship operations.
</details>

### THE TASK

**Primary Objective:** Restore stellar database operations

Create `stellar-database.js`:

```javascript
import { Database } from "bun:sqlite";

// Initialize ship database
const db = new Database("prometheus.db");

// Create essential tables
db.run(`
  CREATE TABLE IF NOT EXISTS systems (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    status TEXT NOT NULL,
    last_check INTEGER NOT NULL
  )
`);

db.run(`
  CREATE TABLE IF NOT EXISTS crew (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    rank TEXT NOT NULL,
    station TEXT NOT NULL
  )
`);

// Prepared statements for security
const insertSystem = db.prepare(`
  INSERT INTO systems (name, status, last_check) 
  VALUES (?, ?, ?)
`);

const getSystemStatus = db.prepare(`
  SELECT * FROM systems WHERE name = ?
`);

const updateSystemStatus = db.prepare(`
  UPDATE systems SET status = ?, last_check = ? WHERE name = ?
`);

// Initialize critical systems
const initializeSystems = db.transaction(() => {
  insertSystem.run("navigation", "online", Date.now());
  insertSystem.run("life-support", "online", Date.now());
  insertSystem.run("communications", "offline", Date.now());
  insertSystem.run("engines", "standby", Date.now());
});

// Execute initialization
initializeSystems();

// System status functions
function checkSystem(systemName) {
  return getSystemStatus.get(systemName);
}

function updateSystem(systemName, status) {
  return updateSystemStatus.run(status, Date.now(), systemName);
}

function getAllSystems() {
  return db.prepare("SELECT * FROM systems ORDER BY name").all();
}

// Test operations
console.log("Stellar Database Online");
console.log("Navigation Status:", checkSystem("navigation"));

// Update communications
updateSystem("communications", "online");
console.log("Communications restored:", checkSystem("communications"));

// Display all systems
console.log("\nAll Ship Systems:");
getAllSystems().forEach(system => {
  console.log(`${system.name}: ${system.status}`);
});

// Cleanup
db.close();
```

### VERIFICATION

Run the database system:
```bash
bun stellar-database.js
```

**Expected Output:**
- Database initialization confirmation
- Navigation system status display
- Communications system update confirmation
- Complete system status list

**Database File Check:**
```bash
ls -la prometheus.db
```
Should show the created database file.

### HINTS
<details>
<summary>If database operations fail</summary>

- Verify SQLite syntax in CREATE TABLE statements
- Check that prepared statements use correct parameter placeholders (?)
- Ensure transaction functions are called correctly
- Use `db.prepare().toString()` to debug SQL statements
</details>

---

## MISSION 04: COSMIC FILE SYSTEM
*Advanced File Operations & Streaming*

**Generate comic panel:**
*Chief Engineer managing flowing data streams represented as rivers of light flowing between crystalline storage nodes. File operations appear as energy conduits with streaming data particles.*

### BRIEFING

The ship's file management system handles everything from configuration files to massive sensor data streams. The system can read files efficiently, stream large datasets, and manage file operations without overwhelming ship resources.

**Success Criteria:**
- File reading operations for multiple formats
- Streaming capability for large files
- File existence verification
- File metadata access
- Efficient memory usage for large datasets

### THINK FIRST

1. **Why use streaming for large files instead of loading everything into memory?**

2. **What's the advantage of lazy-loaded file references versus immediate file reading?**

3. **When would you use `.text()` versus `.json()` versus `.arrayBuffer()`?**

<details>
<summary>Analysis</summary>

1. Streaming prevents memory overflow and allows processing files larger than available RAM - critical for sensor data and logs.

2. Lazy loading only reads files when needed, saving resources and allowing file existence checks without full reads.

3. `.text()` for configuration files, `.json()` for structured data, `.arrayBuffer()` for binary data like images or sensor readings.
</details>

### THE TASK

**Primary Objective:** Restore cosmic file system operations

Create `cosmic-filesystem.js`:

```javascript
// Create test files first
await Bun.write("ship-config.json", JSON.stringify({
  shipName: "Prometheus",
  crew: 150,
  mission: "Deep Space Exploration",
  systems: ["navigation", "life-support", "communications"]
}));

await Bun.write("sensor-log.txt", `
SENSOR LOG - PROMETHEUS
======================
[2024-01-01 00:00:00] Navigation: Coordinates locked
[2024-01-01 00:01:00] Life Support: Oxygen levels nominal
[2024-01-01 00:02:00] Communications: Signal strength optimal
[2024-01-01 00:03:00] Engines: Standby mode active
`);

// Large data simulation
const largeSensorData = "SENSOR_DATA,".repeat(100000) + "END";
await Bun.write("large-sensor-data.txt", largeSensorData);

console.log("Cosmic File System Online\n");

// File operations demonstration
async function demonstrateFileOperations() {
  
  // 1. Basic file information
  const configFile = Bun.file("ship-config.json");
  console.log("=== FILE METADATA ===");
  console.log(`Config file exists: ${await configFile.exists()}`);
  console.log(`Config file size: ${configFile.size} bytes`);
  console.log(`Config file type: ${configFile.type}\n`);
  
  // 2. JSON file reading
  console.log("=== CONFIGURATION DATA ===");
  const config = await configFile.json();
  console.log(`Ship: ${config.shipName}`);
  console.log(`Crew: ${config.crew}`);
  console.log(`Mission: ${config.mission}`);
  console.log(`Systems: ${config.systems.join(", ")}\n`);
  
  // 3. Text file reading
  console.log("=== SENSOR LOGS ===");
  const logFile = Bun.file("sensor-log.txt");
  const logContent = await logFile.text();
  const logLines = logContent.trim().split('\n');
  logLines.forEach(line => {
    if (line.includes('[')) console.log(line);
  });
  console.log();
  
  // 4. Streaming large files
  console.log("=== STREAMING LARGE DATA ===");
  const largeFile = Bun.file("large-sensor-data.txt");
  console.log(`Large file size: ${largeFile.size} bytes`);
  
  const stream = largeFile.stream();
  const reader = stream.getReader();
  let chunks = 0;
  let totalBytes = 0;
  
  try {
    while (true) {
      const { done, value } = await reader.read();
      if (done) break;
      
      chunks++;
      totalBytes += value.length;
      
      // Process first few chunks for demonstration
      if (chunks <= 3) {
        const text = new TextDecoder().decode(value.slice(0, 50));
        console.log(`Chunk ${chunks}: ${text}...`);
      }
    }
  } finally {
    reader.releaseLock();
  }
  
  console.log(`Processed ${chunks} chunks, ${totalBytes} total bytes\n`);
  
  // 5. File writing operations
  console.log("=== FILE OPERATIONS ===");
  const statusFile = Bun.file("system-status.json");
  
  const systemStatus = {
    timestamp: Date.now(),
    systems: {
      navigation: "online",
      lifesupport: "online", 
      communications: "online",
      engines: "standby"
    },
    fileSystemStatus: "operational"
  };
  
  await Bun.write("system-status.json", JSON.stringify(systemStatus, null, 2));
  console.log("System status written to file");
  
  // Verify the write
  const writtenStatus = await Bun.file("system-status.json").json();
  console.log(`Status timestamp: ${new Date(writtenStatus.timestamp)}`);
  console.log(`File system: ${writtenStatus.fileSystemStatus}`);
}

await demonstrateFileOperations();

console.log("\n✓ Cosmic File System fully operational");
```

### VERIFICATION

Run the file system:
```bash
bun cosmic-filesystem.js
```

**Expected Output:**
- File metadata display
- Configuration data parsing
- Sensor log entries
- Streaming operation with chunk processing
- File write confirmation

**File Check:**
```bash
ls -la *.json *.txt
```
Should show all created files with appropriate sizes.

### HINTS
<details>
<summary>If file operations fail</summary>

- Ensure write permissions in the current directory
- Check file paths are correct (relative vs absolute)
- Verify JSON syntax when writing JSON files
- Use `await` with all async file operations
- Check available disk space for large files
</details>

---

## MISSION 05: INTERPLANETARY COMMUNICATION
*WebSocket Implementation & Real-time Data*

**Generate comic panel:**
*Chief Engineer at a communications array with data streams flowing as beams of light between planets. WebSocket connections appear as quantum entanglement links with real-time message packets.*

### BRIEFING

The ship's real-time communication system enables instant coordination between ship systems, crew stations, and potentially other vessels. This system must handle connection upgrades, message routing, and broadcast capabilities for emergency situations.

**Success Criteria:**
- WebSocket server with HTTP upgrade capability
- Real-time bidirectional communication
- Message broadcasting to multiple connections
- Connection lifecycle management
- Per-connection data storage

### THINK FIRST

1. **Why upgrade from HTTP to WebSocket instead of using regular HTTP requests?**

2. **What's the purpose of the `server.upgrade()` function in the fetch handler?**

3. **How does pub/sub messaging help coordinate ship-wide communications?**

<details>
<summary>Analysis</summary>

1. WebSockets provide persistent, low-latency bidirectional communication - essential for real-time ship coordination and emergency responses.

2. `server.upgrade()` transforms an HTTP connection into a WebSocket connection, allowing the same port to handle both protocols.

3. Pub/sub lets systems broadcast to multiple subscribers simultaneously - critical for ship-wide alerts and status updates.
</details>

### THE TASK

**Primary Objective:** Restore interplanetary communication system

Create `communication-hub.js`:

```javascript
const server = Bun.serve({
  port: 3000,
  
  fetch(req, server) {
    const url = new URL(req.url);
    
    // WebSocket upgrade for communication clients
    if (url.pathname === "/comm") {
      const station = url.searchParams.get("station") || "unknown";
      const rank = url.searchParams.get("rank") || "crew";
      
      const upgraded = server.upgrade(req, {
        data: {
          station: station,
          rank: rank,
          connectedAt: Date.now(),
          id: Math.random().toString(36).substr(2, 9)
        }
      });
      
      if (upgraded) {
        return undefined; // Upgrade successful
      }
      
      return new Response("WebSocket upgrade failed", { status: 400 });
    }
    
    // HTTP endpoints for system status
    if (url.pathname === "/") {
      return new Response(`
        Prometheus Communication Hub
        ============================
        Active Connections: ${server.pendingWebSockets}
        
        Connect via WebSocket: ws://localhost:3000/comm?station=bridge&rank=captain
      `);
    }
    
    return new Response("Endpoint not found", { status: 404 });
  },
  
  websocket: {
    data: {} as { 
      station: string, 
      rank: string, 
      connectedAt: number,
      id: string 
    },
    
    open(ws) {
      const { station, rank, id } = ws.data;
      console.log(`[CONN] ${rank} at ${station} connected (${id})`);
      
      // Welcome message
      ws.send(JSON.stringify({
        type: "welcome",
        message: `Welcome to Prometheus Communications, ${rank}`,
        station: station,
        timestamp: Date.now()
      }));
      
      // Subscribe to ship-wide broadcasts
      ws.subscribe("ship-broadcast");
      ws.subscribe(`station-${station}`);
      
      // Notify other stations
      server.publish("ship-broadcast", JSON.stringify({
        type: "station-online",
        station: station,
        rank: rank,
        timestamp: Date.now()
      }));
    },
    
    async message(ws, message) {
      try {
        const data = JSON.parse(message);
        const { station, rank, id } = ws.data;
        
        console.log(`[MSG] ${rank}@${station}: ${data.type}`);
        
        switch (data.type) {
          case "status-request":
            ws.send(JSON.stringify({
              type: "status-response",
              systems: {
                navigation: "online",
                lifesupport: "online",
                communications: "online",
                engines: "standby"
              },
              timestamp: Date.now()
            }));
            break;
            
          case "emergency-alert":
            // Broadcast emergency to all stations
            server.publish("ship-broadcast", JSON.stringify({
              type: "emergency",
              level: data.level || "yellow",
              message: data.message,
              origin: station,
              timestamp: Date.now()
            }));
            break;
            
          case "station-message":
            // Send message to specific station
            const targetStation = data.target;
            server.publish(`station-${targetStation}`, JSON.stringify({
              type: "station-message",
              from: station,
              message: data.message,
              timestamp: Date.now()
            }));
            break;
            
          case "ship-announcement":
            // Broadcast to all stations (command rank only)
            if (rank === "captain" || rank === "commander") {
              server.publish("ship-broadcast", JSON.stringify({
                type: "announcement",
                message: data.message,
                from: `${rank}@${station}`,
                timestamp: Date.now()
              }));
            } else {
              ws.send(JSON.stringify({
                type: "error",
                message: "Insufficient rank for ship-wide announcements"
              }));
            }
            break;
            
          default:
            ws.send(JSON.stringify({
              type: "error",
              message: `Unknown message type: ${data.type}`
            }));
        }
      } catch (error) {
        ws.send(JSON.stringify({
          type: "error",
          message: "Invalid message format"
        }));
      }
    },
    
    close(ws) {
      const { station, rank, id } = ws.data;
      console.log(`[DISC] ${rank} at ${station} disconnected (${id})`);
      
      // Notify other stations
      server.publish("ship-broadcast", JSON.stringify({
        type: "station-offline",
        station: station,
        rank: rank,
        timestamp: Date.now()
      }));
    }
  }
});

console.log(`Prometheus Communication Hub active on ${server.url}`);
console.log("WebSocket endpoint: ws://localhost:3000/comm");
```

Create a test client `comm-client.js`:

```javascript
const ws = new WebSocket("ws://localhost:3000/comm?station=engineering&rank=chief");

ws.onopen = () => {
  console.log("Connected to Communication Hub");
  
  // Test different message types
  setTimeout(() => {
    ws.send(JSON.stringify({ type: "status-request" }));
  }, 1000);
  
  setTimeout(() => {
    ws.send(JSON.stringify({ 
      type: "station-message",
      target: "bridge",
      message: "Engineering systems nominal"
    }));
  }, 2000);
  
  setTimeout(() => {
    ws.send(JSON.stringify({
      type: "emergency-alert",
      level: "yellow",
      message: "Minor power fluctuation in sector 7"
    }));
  }, 3000);
};

ws.onmessage = (event) => {
  const data = JSON.parse(event.data);
  console.log(`[${data.type.toUpperCase()}]`, data.message || data);
};

ws.onclose = () => {
  console.log("Disconnected from Communication Hub");
};
```

### VERIFICATION

1. **Start the communication hub:**
```bash
bun communication-hub.js
```

2. **In another terminal, test the client:**
```bash
bun comm-client.js
```

3. **Test HTTP endpoint:**
```bash
curl http://localhost:3000
```

**Expected Output:**
- Server: Connection logs and message processing
- Client: Welcome message, status response, message confirmations
- HTTP: Communication hub status page

### HINTS
<details>
<summary>If WebSocket connections fail</summary>

- Verify the WebSocket URL format includes proper query parameters
- Check that `server.upgrade()` returns true for successful upgrades
- Ensure JSON message format is valid
- Test with browser developer tools WebSocket inspector
</details>

---

## MISSION 06: WARP SPEED TESTING
*Built-in Test Runner & Performance Optimization*

**Generate comic panel:**
*Chief Engineer running diagnostic tests with holographic test results floating around the engineering bay. Performance metrics appear as energy readings with green checkmarks and red warning indicators.*

### BRIEFING

Before engaging warp drive, all ship systems must pass comprehensive testing protocols. The ship's testing framework validates system functionality, performance benchmarks, and error handling under extreme conditions.

**Success Criteria:**
- Comprehensive test suite for all ship systems
- Performance benchmarks for critical operations
- Mock testing for external dependencies
- Snapshot testing for system configurations
- Concurrent test execution for efficiency

### THINK FIRST

1. **Why run tests before deploying critical ship systems?**

2. **What's the difference between unit tests and integration tests in a starship context?**

3. **When would you use mocks versus real system calls in testing?**

<details>
<summary>Analysis</summary>

1. Tests prevent system failures during critical operations - a navigation error in deep space could be catastrophic.

2. Unit tests verify individual components (single engine), integration tests verify system interactions (engines + navigation + life support).

3. Mocks for testing error conditions safely, external systems that aren't available, or expensive operations. Real calls for final integration verification.
</details>

### THE TASK

**Primary Objective:** Implement comprehensive testing protocols

Create `ship-systems.js` (systems to test):

```javascript
export class NavigationSystem {
  constructor() {
    this.coordinates = { x: 0, y: 0, z: 0 };
    this.destination = null;
  }
  
  setDestination(x, y, z) {
    if (typeof x !== 'number' || typeof y !== 'number' || typeof z !== 'number') {
      throw new Error('Coordinates must be numbers');
    }
    this.destination = { x, y, z };
    return this.destination;
  }
  
  calculateDistance() {
    if (!this.destination) return 0;
    
    const dx = this.destination.x - this.coordinates.x;
    const dy = this.destination.y - this.coordinates.y;
    const dz = this.destination.z - this.coordinates.z;
    
    return Math.sqrt(dx * dx + dy * dy + dz * dz);
  }
  
  async jumpToWarp(factor) {
    if (factor < 1 || factor > 9) {
      throw new Error('Warp factor must be between 1 and 9');
    }
    
    // Simulate warp jump delay
    await new Promise(resolve => setTimeout(resolve, 100));
    
    this.coordinates = { ...this.destination };
    return { status: 'jump-complete', factor, coordinates: this.coordinates };
  }
}

export class LifeSupportSystem {
  constructor() {
    this.oxygenLevel = 100;
    this.temperature = 22;
    this.pressure = 1.0;
  }
  
  getStatus() {
    return {
      oxygen: this.oxygenLevel,
      temperature: this.temperature,
      pressure: this.pressure,
      status: this.oxygenLevel > 20 ? 'nominal' : 'critical'
    };
  }
  
  consumeOxygen(amount) {
    this.oxygenLevel = Math.max(0, this.oxygenLevel - amount);
    return this.oxygenLevel;
  }
  
  replenishOxygen(amount) {
    this.oxygenLevel = Math.min(100, this.oxygenLevel + amount);
    return this.oxygenLevel;
  }
}

export class CommunicationSystem {
  constructor() {
    this.signalStrength = 100;
    this.isOnline = true;
  }
  
  async sendMessage(destination, message) {
    if (!this.isOnline) {
      throw new Error('Communication system offline');
    }
    
    if (this.signalStrength < 10) {
      throw new Error('Signal strength too weak');
    }
    
    // Simulate transmission delay
    await new Promise(resolve => setTimeout(resolve, 50));
    
    return {
      sent: true,
      destination,
      message,
      timestamp: Date.now()
    };
  }
  
  setOffline() {
    this.isOnline = false;
  }
  
  setOnline() {
    this.isOnline = true;
  }
}
```

Create `ship-systems.test.js`:

```javascript
import { test, expect, describe, beforeEach, afterEach, mock, spyOn } from "bun:test";
import { NavigationSystem, LifeSupportSystem, CommunicationSystem } from "./ship-systems.js";

describe("Prometheus Ship Systems", () => {
  
  describe("Navigation System", () => {
    let nav;
    
    beforeEach(() => {
      nav = new NavigationSystem();
