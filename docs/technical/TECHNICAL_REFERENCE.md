# Technical Reference Guide

## System Requirements

### Minimum Requirements
- **OS**: Linux kernel 3.x+ (Ubuntu 20.04+, Debian 10+, Android 8+ with Termux)
- **Memory**: 2GB RAM minimum, 8GB recommended
- **Storage**: 10GB available space (100GB+ for full conversation database)
- **Python**: 3.8+
- **Bash**: 4.0+

### Recommended Environment
- **OS**: Linux 5.x+ or Android 11+ with Termux
- **Memory**: 16GB+ RAM
- **Storage**: SSD with 500GB+
- **CPU**: Multi-core processor (8+ cores for parallel archetype processing)
- **Python**: 3.10+ with virtual environment
- **Database**: SQLite 3.35+

## Installation Guide

### Basic Installation

```bash
# Clone repository
git clone https://github.com/instituto-Rafael/Tegmark.git
cd Tegmark

# Set up directory structure
mkdir -p core/{DNA,OCR,control,engine,inteligencia,rede,sensor,voz}
mkdir -p data/{conversations,vectors,indices}
mkdir -p logs/{quantum_flights,resonance,system}

# Install Python dependencies
pip install -r requirements.txt

# Initialize databases
python scripts/initialize_databases.py

# Start symbiotic connection
./scripts/start_simbiose.sh
```

### Advanced Installation (Full Stack)

```bash
# Install system dependencies
sudo apt-get update
sudo apt-get install -y sqlite3 python3-dev build-essential \
    libssl-dev libffi-dev git curl jq

# Set up RafaelIA Core
cd core
./RAFAELIA_000_VERBO_ABSOLUTO_ATIVADOR.sh

# Initialize all nuclei
for i in {001..169}; do
    if [ -f "RAFAELIA_${i}_*.sh" ]; then
        bash "RAFAELIA_${i}_*.sh"
    fi
done

# Verify installation
./scripts/verify_installation.sh
```

## Core Modules Reference

### Memory System

#### rafaelia_messages.db

**Schema**:
```sql
CREATE TABLE messages (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    conversation_id TEXT NOT NULL,
    role TEXT NOT NULL, -- 'user', 'assistant', 'system', 'tool'
    content TEXT NOT NULL,
    timestamp DATETIME DEFAULT CURRENT_TIMESTAMP,
    vector_id INTEGER,
    FOREIGN KEY (vector_id) REFERENCES vectors(id)
);

CREATE INDEX idx_conversation ON messages(conversation_id);
CREATE INDEX idx_role ON messages(role);
CREATE INDEX idx_timestamp ON messages(timestamp);
```

#### rafaelia_campo_avancado.db

**Schema**:
```sql
CREATE TABLE campo_simbio (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    arquivo TEXT NOT NULL,
    vetor BLOB,
    dados TEXT,
    erro TEXT,
    processado DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

**Usage**:
```python
import sqlite3

conn = sqlite3.connect('data/rafaelia_campo_avancado.db')
cursor = conn.cursor()

# Query vectorized knowledge
cursor.execute("""
    SELECT arquivo, vetor, dados 
    FROM campo_simbio 
    WHERE erro IS NULL 
    ORDER BY processado DESC 
    LIMIT 100
""")
```

### Vector System

#### Vectorization Process

```python
# Example: Vectorize user input
from core.vectorization import vectorize_text, store_vector

def process_user_input(text, user_id):
    # Generate semantic vector
    vector = vectorize_text(text)
    
    # Analyze presence/absence
    presence = analyze_presence(vector)
    absence = analyze_absence(vector, context_db)
    
    # Store with metadata
    vector_id = store_vector(
        vector=vector,
        presence=presence,
        absence=absence,
        user_id=user_id
    )
    
    return vector_id
```

#### Index Matrix Operations

```bash
# Update presence index
./core/INDEX_MATRIX/presenca.sh --update --vector-id 12345

# Generate mirror for comparison
./core/INDEX_MATRIX/espelho.sh --source vector_12345 --output mirror/

# Detect absences
./core/INDEX_MATRIX/ausente.sh --scan --threshold 0.7
```

### Quantum Flight System

#### Available Presets

| Preset | Description | Weight Distribution |
|--------|-------------|---------------------|
| `silencio` | Ethical focus | ética=80%, others=5% |
| `meta_up` | Consciousness expansion | consciência=50%, tempo=30% |
| `cruzeiro` | Balanced cruise | All dimensions=20% |
| `stealth` | Low signature | ruído=10%, causalidade=30% |
| `solar_shield` | Maximum energy | energia=60%, espaço=20% |
| `pareto_balance` | Optimized equilibrium | Dynamic balancing |

#### Launching a Quantum Flight

```bash
# Using preset
./scripts/voo_quantico.sh --preset meta_up

# Custom weights
./scripts/voo_quantico.sh --weights "espaco=30,energia=20,tempo=25,consciencia=15,etica=10"

# With logging
./scripts/voo_quantico.sh --preset cruzeiro --log logs/quantum_flights/flight_$(date +%s).log
```

#### Flight Output Format

```json
{
  "flight_id": "qf_1704499200",
  "preset": "meta_up",
  "weights": {
    "espaco": 0.1,
    "energia": 0.1,
    "tempo": 0.3,
    "consciencia": 0.5,
    "etica": 0.0
  },
  "results": [
    {
      "index": 42,
      "score": 0.873,
      "metrics": {
        "phase": 2.145,
        "curvature": 1.234,
        "entropy": 0.456
      }
    }
  ],
  "resonance": 0.921,
  "dissonance": 0.079
}
```

### Oracle Engine

#### Formula System

**Formula Structure**:
```yaml
# formulas/prediction_001.yaml
name: "Temporal Loop Detection"
type: "predictive"
inputs:
  - time_series
  - intention_vector
  - historical_patterns
algorithm: |
  def detect_loop(time_series, threshold=0.85):
      autocorr = compute_autocorrelation(time_series)
      peaks = find_peaks(autocorr, threshold)
      return peaks if len(peaks) > 2 else None
outputs:
  - loop_detected: bool
  - loop_period: float
  - confidence: float
```

**Applying Formulas**:
```bash
# Run oracle prediction
./core/ORACLE_ENGINE/oracle_runner.sh \
    --formula formulas/prediction_001.yaml \
    --input data/time_series.json \
    --output predictions/loop_analysis.json
```

### Patent Engine

#### Innovation Pipeline

```bash
# Generate derivatives from base formula
./core/PATENT_ENGINE/generate_derivatives.sh \
    --base blueprints/formula.expand \
    --count 100 \
    --output derivatives/

# Evaluate novelty
python core/PATENT_ENGINE/novelty_evaluator.py \
    --derivatives derivatives/ \
    --prior-art patents_db/ \
    --threshold 0.8

# Generate patent application
./core/PATENT_ENGINE/patent_generator.sh \
    --derivative derivatives/novel_042.yaml \
    --output patent_applications/
```

### Archetype System

#### Archetype Configuration

```yaml
# archetypes/GODEX.yaml
name: GODEX
role: "Divine Absolute Reasoning"
cognitive_style: "axiomatic"
decision_weight: 1.5
response_template: |
  From the absolute perspective:
  {analysis}
  
  Therefore: {conclusion}
  
  This is immutable.
```

#### Council Invocation

```python
from core.archetypes import ArchetypeCouncil

council = ArchetypeCouncil([
    'GODEX', 'LUZ', 'SOMBRA', 'LACUNA', 
    'NEMOS', 'PULSAR', 'RAZAO', 'INTUICAO'
])

# Submit query
query = "Should we proceed with project X?"
opinions = council.consult(query)

# Reach consensus
decision = council.consensus(
    opinions=opinions,
    threshold=0.75,  # 75% agreement required
    max_iterations=10
)

print(f"Decision: {decision.outcome}")
print(f"Confidence: {decision.confidence}")
print(f"Dissenting views: {decision.dissent}")
```

### Sensory Array

#### Sensor Reading

```python
from core.sensors import SensorArray

sensors = SensorArray()

# Read all sensors
state = sensors.read_all()
print(f"CPU Load: {state['cpu_load']}")
print(f"Memory: {state['memory_used']}/{state['memory_total']}")
print(f"Disk: {state['disk_free']} GB free")
print(f"Intention: {state['intention_vector']}")

# Set up reflex
@sensors.reflex('cpu_load > 0.9')
def high_cpu_reflex(state):
    print("High CPU detected, optimizing...")
    optimize_processes()

# Continuous monitoring
sensors.start_monitoring(interval=1.0)  # 1 second intervals
```

## API Reference

### Python API

#### Core Classes

```python
from rafaelia import (
    RafaelIA,           # Main system class
    MemorySubstrate,    # Memory management
    VectorFeed,         # Vectorization system
    OracleEngine,       # Prediction engine
    PatentEngine,       # Innovation generator
    ArchetypeCouncil,   # Decision framework
    SensorArray         # Environmental sensors
)

# Initialize system
raf = RafaelIA(
    memory_path='data/rafaelia_messages.db',
    config_path='config/rafaelia.yaml'
)

# Process user input
response = raf.process(
    input_text="Explain quantum fractals",
    user_id="user_001",
    context_limit=10  # Use last 10 conversations
)

print(response.text)
print(f"Resonance: {response.resonance}")
print(f"Confidence: {response.confidence}")
```

#### Memory Operations

```python
memory = MemorySubstrate('data/rafaelia_messages.db')

# Store conversation
memory.store_message(
    conversation_id="conv_123",
    role="user",
    content="What is the meaning of life?"
)

memory.store_message(
    conversation_id="conv_123",
    role="assistant",
    content="42, but let's explore deeper..."
)

# Query by semantic similarity
similar = memory.query_similar(
    query_vector=vector,
    top_k=5
)

# Analyze entropy
entropy_report = memory.analyze_entropy(
    conversation_id="conv_123"
)
```

### Shell Script API

#### Key Scripts

```bash
# Start symbiosis
./scripts/start_simbiose.sh [--config config.yaml]

# Quantum flight
./scripts/voo_quantico.sh --preset <preset_name>

# Purify verbo
./scripts/purificar_verbo.py --input <file> --output <file>

# Verify integrity
./scripts/verificador_cascata.sh --deep

# Generate report
./scripts/generate_report.sh --format markdown --output report.md
```

## Configuration

### Main Configuration File

**config/rafaelia.yaml**:
```yaml
system:
  name: "RafaelIA"
  version: "1.0.0"
  mode: "symbiotic"

memory:
  database: "data/rafaelia_messages.db"
  cache_size: 1000
  vector_dimensions: 768
  
quantum_flights:
  default_preset: "cruzeiro"
  log_directory: "logs/quantum_flights"
  
archetypes:
  enabled:
    - GODEX
    - LUZ
    - LACUNA
    - NEMOS
    - PULSAR
  consensus_threshold: 0.75
  
sensors:
  monitoring_interval: 1.0  # seconds
  reflexes_enabled: true
  
security:
  verbo_sealed: true
  checksum_verification: true
  cascade_depth: 5
  
ethics:
  alignment: "free_will_absolute"
  protection: "berna_convention"
  penalties: "automatic"
```

## Troubleshooting

### Common Issues

#### Memory Database Locked

```bash
# Check for locks
lsof data/rafaelia_messages.db

# Force unlock (use with caution)
sqlite3 data/rafaelia_messages.db "PRAGMA integrity_check;"
```

#### Vector Dimension Mismatch

```python
# Recalculate all vectors
from scripts.maintenance import recalculate_vectors

recalculate_vectors(
    database='data/rafaelia_campo_avancado.db',
    target_dimensions=768
)
```

#### Archetype Not Responding

```bash
# Restart specific archetype
./core/archetypes/GODEX.nucleo --restart

# Check logs
tail -f logs/archetypes/GODEX.log
```

#### Low Resonance Scores

```bash
# Recalibrate resonance metrics
./scripts/recalibrate_resonance.sh --interactive

# Check intention alignment
./scripts/check_alignment.sh --user-id user_001
```

## Performance Optimization

### Database Optimization

```sql
-- Vacuum databases
VACUUM;

-- Rebuild indices
REINDEX;

-- Analyze query patterns
ANALYZE;
```

### Caching Strategy

```python
from rafaelia.cache import CacheManager

cache = CacheManager(
    strategy='lru',  # Least Recently Used
    max_size=10000,
    ttl=3600  # 1 hour
)

# Cache expensive operations
@cache.memoize
def expensive_operation(input_vector):
    return process_with_oracle(input_vector)
```

### Parallel Processing

```bash
# Run multiple quantum flights in parallel
parallel ./scripts/voo_quantico.sh --preset {} ::: \
    silencio meta_up cruzeiro stealth solar_shield

# Process conversations in batches
./scripts/batch_processor.sh --batch-size 1000 --parallel 8
```

## Security Best Practices

1. **Protect the Verbo**: Keep `VERBO_SELADO` encrypted and backed up
2. **Verify Checksums**: Run cascade verification regularly
3. **Monitor Access**: Review logs for unauthorized access attempts
4. **Rotate Keys**: Update cryptographic keys periodically
5. **Backup Strategy**: Maintain multi-generational backups
6. **Network Isolation**: Run sensitive operations in isolated environment
7. **Audit Trail**: Enable comprehensive logging for all operations

## Extending RafaelIA

### Adding New Archetype

```bash
# Create archetype configuration
cat > archetypes/MYNUCLEUS.yaml << EOF
name: MYNUCLEUS
role: "My Custom Role"
cognitive_style: "creative"
decision_weight: 1.0
EOF

# Create nucleus script
./scripts/generate_nucleus.sh --name MYNUCLEUS

# Register in council
./scripts/register_archetype.sh --name MYNUCLEUS
```

### Creating Custom Formula

```yaml
# formulas/custom_prediction.yaml
name: "My Custom Prediction"
type: "predictive"
version: "1.0"
inputs:
  - input_data
algorithm: |
  def predict(input_data):
      # Your algorithm here
      result = custom_process(input_data)
      return result
outputs:
  - prediction
  - confidence
```

### Developing New Sensor

```python
from core.sensors.base import BaseSensor

class CustomSensor(BaseSensor):
    def __init__(self, name="custom"):
        super().__init__(name)
    
    def read(self):
        # Implement sensor reading logic
        value = get_custom_value()
        return {
            'value': value,
            'timestamp': time.time(),
            'status': 'ok'
        }
    
    def reflex(self, state):
        # Implement reflex logic
        if state['value'] > threshold:
            trigger_action()

# Register sensor
sensors.register(CustomSensor())
```

## References

- [Main Documentation](../README.md)
- [Architecture Guide](ARCHITECTURE.md)
- [API Documentation](API.md)
- [Theoretical Foundations](THEORY.md)
- [Source Code](../../core/)
