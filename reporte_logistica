import datetime

# Simulamos una base de datos de incidentes en formato de lista de diccionarios
# (Esto simula los datos extraídos de un Excel o sistema de monitoreo de rutas)
incidentes_raw = [
    {"id": 101, "unidad": "T-04", "operador": "Carlos Lopez", "incidencia": "Falla mecanica", "estatus": "Rescatado", "prioridad": "Alta"},
    {"id": 102, "unidad": "T-12", "operador": "Juan Perez", "incidencia": "Retraso por trafico", "estatus": "En ruta", "prioridad": "Baja"},
    {"id": 103, "unidad": "", "operador": "Invalido", "incidencia": "Error de sistema", "estatus": "Cancelado", "prioridad": "Baja"}, # Registro corrupto
    {"id": 104, "unidad": "T-08", "operador": "Mario Gomez", "incidencia": "Bloqueo de carretera", "estatus": "Rescatado", "prioridad": "Alta"}
]

def procesar_reporte(datos):
    print("Iniciando procesamiento remoto de incidencias...")
    reporte_limpio = []
    rescates_criticos = 0

    for incidente in datos:
        # Validación de datos: Omitir registros corruptos (sin número de unidad)
        if not incidente["unidad"]:
            continue
        
        # Filtrado lógico
        if incidente["prioridad"] == "Alta" and incidente["estatus"] == "Rescatado":
            rescates_criticos += 1
            
        reporte_limpio.append(incidente)
    
    # Generar el output estructurado del reporte
    
    print(f"REPORTES DE LOGÍSTICA GENERADO - {datetime.date.today()}")
    print("-" * 20)
    print(f"Total de incidentes válidos procesados: {len(reporte_limpio)}")
    print(f"Rescates críticos coordinados exitosamente: {rescates_criticos}")
    print("-" * 40)
    
    for item in reporte_limpio:
        print(f"Unidad {item['unidad']} | Operador: {item['operador']} | Diagnóstico: {item['incidencia']} [{item['prioridad']}]")
    

if __name__ == "__main__":
    procesar_reporte(incidentes_raw)
