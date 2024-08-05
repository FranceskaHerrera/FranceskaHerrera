import matplotlib.pyplot as plt
import networkx as nx

# Crear un grafo dirigido
G = nx.DiGraph()

# Añadir nodos de los abuelos
G.add_node("Abuelo (XY)")
G.add_node("Abuela (XX)")

# Añadir nodos de los padres
G.add_node("Padre (XY)")
G.add_node("Madre (XX)")

# Añadir nodos de los hijos
G.add_node("Hijo (XY)")
G.add_node("Hija (XX)")

# Añadir nodos de los nietos
G.add_node("Nieto (XY)")
G.add_node("Nieta (XX)")

# Añadir aristas (conexiones)
# De abuelos a padres
G.add_edge("Abuelo (XY)", "Padre (XY)")
G.add_edge("Abuela (XX)", "Padre (XY)")
G.add_edge("Abuelo (XY)", "Madre (XX)")
G.add_edge("Abuela (XX)", "Madre (XX)")

# De padres a hijos
G.add_edge("Padre (XY)", "Hijo (XY)")
G.add_edge("Madre (XX)", "Hijo (XY)")
G.add_edge("Padre (XY)", "Hija (XX)")
G.add_edge("Madre (XX)", "Hija (XX)")

# De hijos a nietos
G.add_edge("Hijo (XY)", "Nieto (XY)")
G.add_edge("Hija (XX)", "Nieto (XY)")
G.add_edge("Hijo (XY)", "Nieta (XX)")
G.add_edge("Hija (XX)", "Nieta (XX)")

# Dibujar el grafo
plt.figure(figsize=(12, 8))
pos = nx.spring_layout(G)  # Para una mejor visualización
nx.draw(G, pos, with_labels=True, node_size=3000, node_color="lightblue", font_size=10, font_weight="bold", arrows=True, arrowstyle='-|>', arrowsize=20)
plt.title("Herencia Cromosómica de Padres a Hijos y Nietos")
plt.show()

