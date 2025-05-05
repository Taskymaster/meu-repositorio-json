<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestão de Contratos 2025 | SINC Contratações</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #2c5282;
            --secondary-color: #4299e1;
            --accent-color: #3182ce;
            --dark-gray: #2d3748;
            --medium-gray: #4a5568;
            --light-gray: #e2e8f0;
            --success-color: #48bb78;
            --warning-color: #ed8936;
            --danger-color: #e53e3e;
            --info-color: #4299e1;
            --text-light: #f7fafc;
            --text-dark: #1a202c;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f8fafc;
            color: var(--text-dark);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .header {
            background-color: var(--primary-color);
            color: white;
            padding: 1.5rem;
            margin-bottom: 2rem;
            border-radius: 8px;
            box-shadow: var(--shadow);
            text-align: center;
        }

        .header h2 {
            color: var(--text-light);
            margin: 0;
            font-size: 1.5em;
            font-weight: 600;
            line-height: 1.4;
        }

        .section-title {
            color: var(--primary-color);
            margin: 2rem 0 1rem;
            font-size: 1.5rem;
            font-weight: 600;
            text-align: center;
        }

        .error-message {
            padding: 15px;
            border-radius: 8px;
            margin: 1rem 0;
            text-align: center;
            font-weight: 600;
            font-size: 1.1em;
            box-shadow: var(--shadow);
            background-color: #fff5f5;
            color: var(--danger-color);
            border-left: 5px solid var(--danger-color);
        }

        .accordion-error {
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 1rem 1.5rem;
            border-radius: 8px;
            margin: 1rem 0;
            font-weight: 600;
            font-size: 1rem;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border-left-width: 5px;
            border-left-style: solid;
            background-color: #fff5f5;
            color: var(--danger-color);
            border-left-color: var(--danger-color);
        }

        .accordion-error:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
        }

        .accordion-error.sem-dados {
            background-color: #f7fafc;
            color: var(--medium-gray);
            border-left-color: var(--light-gray);
        }

        .accordion-arrow {
            font-size: 1.2em;
            color: currentColor;
            transition: transform 0.2s;
        }

        .accordion-error.open .accordion-arrow {
            transform: rotate(90deg);
        }

        .row-count {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background-color: rgba(0, 0, 0, 0.1);
            border-radius: 20px;
            padding: 2px 10px;
            margin-left: 10px;
            font-size: 0.85em;
            font-weight: 600;
            min-width: 24px;
        }

        .accordion-details {
            display: none;
            animation: fadeIn 0.3s ease;
            background-color: white;
            border-radius: 8px;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
            overflow: hidden;
        }

        .accordion-details.open {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .input-section {
            background-color: #f9fafb;
            padding: 1.5rem;
            margin: 1rem;
            border-radius: 8px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
            display: none;
            border-top: 3px solid var(--secondary-color);
        }

        .input-section.visible {
            display: block;
        }

        .input-section textarea {
            width: 100%;
            height: 120px;
            margin: 1rem 0;
            padding: 12px;
            border: 1px solid #e2e8f0;
            border-radius: 6px;
            font-family: 'Consolas', 'Monaco', monospace;
            font-size: 0.9rem;
            resize: vertical;
            transition: var(--transition);
        }

        .input-section textarea:focus {
            outline: none;
            border-color: var(--secondary-color);
            box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.2);
        }

        .horizontal-scroll {
            overflow-x: auto;
            padding: 1.5rem;
            background-color: white;
            border-radius: 0 0 8px 8px;
        }

        .data-grid {
            min-width: 100%;
            border-collapse: collapse;
            border-spacing: 0;
            font-size: 0.95rem;
        }

        .data-grid th {
            background-color: #f1f5f9;
            padding: 12px 16px;
            text-align: left;
            font-weight: 600;
            color: var(--dark-gray);
            border-bottom: 2px solid #e2e8f0;
            white-space: nowrap;
        }

        .data-grid td {
            padding: 12px 16px;
            border-bottom: 1px solid #e2e8f0;
            white-space: nowrap;
            color: var(--medium-gray);
        }

        .data-grid tr:hover td {
            background-color: #f8fafc;
        }

        .actions {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin: 1.5rem 0;
            padding: 0 1.5rem;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 0.5rem 1.25rem;
            font-size: 0.95rem;
            font-weight: 500;
            border-radius: 6px;
            border: none;
            cursor: pointer;
            transition: var(--transition);
            text-decoration: none;
            gap: 8px;
        }

        .toggle-input-btn {
            background-color: var(--secondary-color);
            color: white;
        }

        .toggle-input-btn:hover {
            background-color: var(--accent-color);
        }

        .process-btn {
            background-color: var(--success-color);
            color: white;
        }

        .process-btn:hover {
            background-color: #38a169;
        }

        .back-btn {
            background-color: var(--primary-color);
            color: white;
        }

        .back-btn:hover {
            background-color: #2a4365;
        }

        .delete-btn {
            background-color: var(--danger-color);
            color: white;
            padding: 0.35rem 0.75rem;
            font-size: 0.85rem;
            border-radius: 4px;
        }

        .delete-btn:hover {
            background-color: #c53030;
        }

        .download-btn {
            background-color: var(--medium-gray);
            color: white;
        }

        .download-btn:hover {
            background-color: #2d3748;
        }

        .section-divider {
            border: none;
            height: 1px;
            background-color: #e2e8f0;
            margin: 2.5rem 0;
        }

        /* CSS para os filtros de CNPJ */
        #filtros-container {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 2rem;
        }
        
        .filtro-cnpj {
            background-color: white;
            padding: 1.25rem;
            border-radius: 8px;
            box-shadow: var(--shadow);
            display: flex;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        .filtro-cnpj label {
            font-weight: 600;
            color: var(--dark-gray);
        }
        
        .filtro-cnpj select {
            padding: 0.5rem 1rem;
            border: 1px solid #e2e8f0;
            border-radius: 6px;
            flex-grow: 1;
            max-width: 350px;
            font-size: 0.95rem;
            color: var(--dark-gray);
            background-color: #f9fafb;
            transition: var(--transition);
        }

        .filtro-cnpj select:focus {
            outline: none;
            border-color: var(--secondary-color);
            box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.2);
        }
        
        .reset-btn {
            background-color: var(--medium-gray);
            color: white;
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 500;
            transition: var(--transition);
        }
        
        .reset-btn:hover {
            background-color: #2d3748;
        }

        .icon-btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .icon-btn i {
            font-size: 1rem;
        }

        .year-badge {
            display: inline-block;
            background-color: var(--primary-color);
            color: white;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
            margin-left: 10px;
        }
        
        @media (max-width: 768px) {
            .filtro-cnpj {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .filtro-cnpj select {
                width: 100%;
                max-width: 100%;
            }

            .actions {
                flex-wrap: wrap;
            }

            .btn {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h2>MUNICÍPIO DE SAO LUIS - CNPJ: 06307102000130 - EXERCÍCIO: 2025</h2>
            <h2>Layout: CONTRATO <span class="year-badge">2025</span></h2>
            <div class="actions">
                <button class="btn download-btn icon-btn" onclick="downloadJSON()"><i class="fas fa-download"></i> Download JSON</button>
                <button class="btn download-btn icon-btn" onclick="baixarPDF()"><i class="fas fa-file-pdf"></i> Baixar PDF</button>
                <label for="importar-json" class="btn download-btn icon-btn" style="background-color: var(--success-color); cursor: pointer;"><i class="fas fa-upload"></i> Importar JSON</label>
                <input type="file" id="importar-json" accept=".json" style="display: none;" onchange="importarJSON(event)">
                <button class="btn download-btn icon-btn" style="background-color: var(--info-color); cursor: pointer;" onclick="carregarDadosJSON()"><i class="fas fa-cloud-download-alt"></i> Carregar do GitHub</button>
                <a href="dashboard.html" class="btn back-btn icon-btn"><i class="fas fa-arrow-left"></i> Voltar ao Painel</a>
            </div>
        </div>

        <!-- Filtros por CNPJ -->
        <div id="filtros-container">
            <!-- Filtro por CNPJ UG - aparece apenas quando há mais de um CNPJ UG -->
            <div id="filtro-cnpj-ug-container" class="filtro-cnpj" style="display: none;">
                <label for="filtro-cnpj-ug"><i class="fas fa-filter"></i> Filtrar por CNPJ UG:</label>
                <select id="filtro-cnpj-ug" onchange="filtrarPorCNPJUG()">
                    <option value="">Todos os CNPJs UG</option>
                </select>
                <button class="reset-btn icon-btn" onclick="resetarFiltroCNPJUG()"><i class="fas fa-times"></i> Limpar Filtro</button>
            </div>
            
            <!-- Filtro por CNPJ Contratante - aparece apenas quando há mais de um CNPJ Contratante -->
            <div id="filtro-cnpj-contratante-container" class="filtro-cnpj" style="display: none;">
                <label for="filtro-cnpj-contratante"><i class="fas fa-filter"></i> Filtrar por CNPJ Contratante:</label>
                <select id="filtro-cnpj-contratante" onchange="filtrarPorCNPJContratante()">
                    <option value="">Todos os CNPJs Contratantes</option>
                </select>
                <button class="reset-btn icon-btn" onclick="resetarFiltroCNPJContratante()"><i class="fas fa-times"></i> Limpar Filtro</button>
            </div>
        </div>

        <h3 class="section-title">Contratos com Pendências - Exercício 2025</h3>

        <!-- Primeira Seção - CPF/CNPJ -->
        <div class="accordion-error" onclick="toggleAccordion('1', this)">
            <span><i class="fas fa-id-card"></i> ERRO! O código do CPF/CNPJ informado para 'contratado' é inválido <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-1">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>

        <div class="accordion-details" id="accordion-details-1">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('1')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-1">
                <textarea id="input-dados-1" placeholder="Cole aqui os dados no formato:&#10;CNPJ UG    ID Contrato    ID Contrato PNCP    CNPJ Procedimento    ID Contratação    Número Contrato    Ano Contrato    CPF CNPJ    Número Processo    Ano Processo    Objeto    Data Assinatura    Data Publicação    Data Início    Data Fim    CPF Autoridade    Valor    CNPJ Envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('1')"><i class="fas fa-check-circle"></i> Processar Dados</button>
                </div>
            </div>
            <div class="horizontal-scroll">
                <table class="data-grid">
                    <thead>
                        <tr>
                            <th>CNPJ UG</th>
                            <th>ID Contrato</th>
                            <th>ID Contrato PNCP</th>
                            <th>CNPJ Procedimento</th>
                            <th>ID Contratação</th>
                            <th>Número Contrato</th>
                            <th>Ano Contrato</th>
                            <th>CPF CNPJ</th>
                            <th>Número Processo</th>
                            <th>Ano Processo</th>
                            <th>Objeto</th>
                            <th>Data Assinatura</th>
                            <th>Data Publicação</th>
                            <th>Data Início</th>
                            <th>Data Fim</th>
                            <th>CPF Autoridade</th>
                            <th>Valor</th>
                            <th>CNPJ Envio</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="dados-body-1"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Segunda Seção - Data Assinatura -->
        <div class="accordion-error" onclick="toggleAccordion('2', this)">
            <span><i class="fas fa-calendar-alt"></i> ERRO! A 'data_assinatura' não pode ser superior à 'data_inicio' <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-2">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>

        <div class="accordion-details" id="accordion-details-2">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('2')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-2">
                <textarea id="input-dados-2" placeholder="Cole aqui os dados no formato:&#10;CNPJ UG    ID Contrato    ID Contrato PNCP    CNPJ Procedimento    ID Contratação    Número Contrato    Ano Contrato    CPF CNPJ    Número Processo    Ano Processo    Objeto    Data Assinatura    Data Publicação    Data Início    Data Fim    CPF Autoridade    Valor    CNPJ Envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('2')"><i class="fas fa-check-circle"></i> Processar Dados</button>
                </div>
            </div>
            <div class="horizontal-scroll">
                <table class="data-grid">
                    <thead>
                        <tr>
                            <th>CNPJ UG</th>
                            <th>ID Contrato</th>
                            <th>ID Contrato PNCP</th>
                            <th>CNPJ Procedimento</th>
                            <th>ID Contratação</th>
                            <th>Número Contrato</th>
                            <th>Ano Contrato</th>
                            <th>CPF CNPJ</th>
                            <th>Número Processo</th>
                            <th>Ano Processo</th>
                            <th>Objeto</th>
                            <th>Data Assinatura</th>
                            <th>Data Publicação</th>
                            <th>Data Início</th>
                            <th>Data Fim</th>
                            <th>CPF Autoridade</th>
                            <th>Valor</th>
                            <th>CNPJ Envio</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="dados-body-2"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Terceira Seção - Documento Comprobatório -->
        <div class="accordion-error" onclick="toggleAccordion('3', this)">
            <span><i class="fas fa-file-alt"></i> ERRO! Documento comprobatório não apresentado <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-3">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>

        <div class="accordion-details" id="accordion-details-3">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('3')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-3">
                <textarea id="input-dados-3" placeholder="Cole aqui os dados no formato:&#10;CNPJ UG    ID Contrato    ID Contrato PNCP    CNPJ Procedimento    ID Contratação    Número Contrato    Ano Contrato    CPF CNPJ    Número Processo    Ano Processo    Objeto    Data Assinatura    Data Publicação    Data Início    Data Fim    CPF Autoridade    Valor    CNPJ Envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('3')"><i class="fas fa-check-circle"></i> Processar Dados</button>
                </div>
            </div>
            <div class="horizontal-scroll">
                <table class="data-grid">
                    <thead>
                        <tr>
                            <th>CNPJ UG</th>
                            <th>ID Contrato</th>
                            <th>ID Contrato PNCP</th>
                            <th>CNPJ Procedimento</th>
                            <th>ID Contratação</th>
                            <th>Número Contrato</th>
                            <th>Ano Contrato</th>
                            <th>CPF CNPJ</th>
                            <th>Número Processo</th>
                            <th>Ano Processo</th>
                            <th>Objeto</th>
                            <th>Data Assinatura</th>
                            <th>Data Publicação</th>
                            <th>Data Início</th>
                            <th>Data Fim</th>
                            <th>CPF Autoridade</th>
                            <th>Valor</th>
                            <th>CNPJ Envio</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="dados-body-3"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Quarta Seção - Integridade Referencial -->
        <div class="accordion-error" onclick="toggleAccordion('4', this)">
            <span><i class="fas fa-link"></i> ERRO DE INTEGRIDADE REFERENCIAL! O 'id_procedimento' não tem correspondente no layout PROCEDIMENTO_LICITATORIO, PROCEDIMENTO_CONTRATACAO ou PROCEDIMENTO_ADESAO <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-4">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>

        <div class="accordion-details" id="accordion-details-4">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('4')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-4">
                <textarea id="input-dados-4" placeholder="Cole aqui os dados no formato:&#10;CNPJ UG    ID Contrato    ID Contrato PNCP    CNPJ Procedimento    ID Contratação    Número Contrato    Ano Contrato    CPF CNPJ    Número Processo    Ano Processo    Objeto    Data Assinatura    Data Publicação    Data Início    Data Fim    CPF Autoridade    Valor    CNPJ Envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('4')"><i class="fas fa-check-circle"></i> Processar Dados</button>
                </div>
            </div>
            <div class="horizontal-scroll">
                <table class="data-grid">
                    <thead>
                        <tr>
                            <th>CNPJ UG</th>
                            <th>ID Contrato</th>
                            <th>ID Contrato PNCP</th>
                            <th>CNPJ Procedimento</th>
                            <th>ID Contratação</th>
                            <th>Número Contrato</th>
                            <th>Ano Contrato</th>
                            <th>CPF CNPJ</th>
                            <th>Número Processo</th>
                            <th>Ano Processo</th>
                            <th>Objeto</th>
                            <th>Data Assinatura</th>
                            <th>Data Publicação</th>
                            <th>Data Início</th>
                            <th>Data Fim</th>
                            <th>CPF Autoridade</th>
                            <th>Valor</th>
                            <th>CNPJ Envio</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="dados-body-4"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>
        <div class="header">
            <h2>ALTERACAO_CONTRATUAL <span class="year-badge">2025</span></h2>
        </div>

        <h3 class="section-title">Alterações Contratuais com Pendências</h3>

        <div class="accordion-error" onclick="toggleAccordion('alteracao1', this)">
            <span><i class="fas fa-file-contract"></i> ERRO! Documento comprobatório não apresentado <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-alteracao1">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>

        <div class="accordion-details" id="accordion-details-alteracao1">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('alteracao1')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-alteracao1">
                <textarea id="input-dados-alteracao1" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('alteracao1')"><i class="fas fa-check-circle"></i> Processar Dados</button>
                </div>
            </div>
            <div class="horizontal-scroll">
                <table class="data-grid">
                    <thead>
                        <tr>
                            <th>cnpj_contratante</th>
                            <th>id_contrato</th>
                            <th>tipo_termo</th>
                            <th>numero_termo</th>
                            <th>ano_termo</th>
                            <th>contratado</th>
                            <th>numero_processo</th>
                            <th>ano_processo</th>
                            <th>objeto</th>
                            <th>data_assinatura</th>
                            <th>data_publicacao</th>
                            <th>data_inicio</th>
                            <th>data_fim</th>
                            <th>cpf_autoridade</th>
                            <th>valor</th>
                            <th>cnpj_envio</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="dados-body-alteracao1"></tbody>
                </table>
            </div>
        </div>

        <div class="accordion-error" onclick="toggleAccordion('alteracao2', this)">
            <span><i class="fas fa-link-slash"></i> ERRO DE INTEGRIDADE REFERENCIAL! O 'id_contrato' não tem correspondente no layout CONTRATO <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-alteracao2">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>

        <div class="accordion-details" id="accordion-details-alteracao2">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('alteracao2')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-alteracao2">
                <textarea id="input-dados-alteracao2" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('alteracao2')"><i class="fas fa-check-circle"></i> Processar Dados</button>
                </div>
            </div>
            <div class="horizontal-scroll">
                <table class="data-grid">
                    <thead>
                        <tr>
                            <th>cnpj_contratante</th>
                            <th>id_contrato</th>
                            <th>tipo_termo</th>
                            <th>numero_termo</th>
                            <th>ano_termo</th>
                            <th>contratado</th>
                            <th>numero_processo</th>
                            <th>ano_processo</th>
                            <th>objeto</th>
                            <th>data_assinatura</th>
                            <th>data_publicacao</th>
                            <th>data_inicio</th>
                            <th>data_fim</th>
                            <th>cpf_autoridade</th>
                            <th>valor</th>
                            <th>cnpj_envio</th>
                            <th>Ações</th>
                        </tr>
                    </thead>
                    <tbody id="dados-body-alteracao2"></tbody>
                </table>
            </div>
        </div>

        <div class="actions">
            <a href="dashboard.html" class="btn back-btn icon-btn"><i class="fas fa-arrow-left"></i> Voltar ao Painel</a>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <script>
        // Função para migrar dados antigos
        function processarDados(secao) {
            const textarea = document.getElementById(`input-dados-${secao}`);
            const tbody = document.getElementById(`dados-body-${secao}`);
            const linhas = textarea.value.trim().split('\n');
            
            // Contador para linhas adicionadas
            let linhasAdicionadas = 0;
            
            // Definir colunas específicas para as seções alteracao1 e alteracao2
            let headers = ['cnpj_ug', 'id_contrato', 'id_contrato_pncp', 'cnpj_procedimento', 'id_contratacao', 'numero_contrato', 'ano_contrato', 'cpf_cnpj', 'numero_processo', 'ano_processo', 'objeto', 'data_assinatura', 'data_publicacao', 'data_inicio', 'data_fim', 'cpf_autoridade', 'valor', 'cnpj_envio'];
            if (secao === 'alteracao1' || secao === 'alteracao2') {
                headers = ['cnpj_contratante', 'id_contrato', 'tipo_termo', 'numero_termo', 'ano_termo', 'contratado', 'numero_processo', 'ano_processo', 'objeto', 'data_assinatura', 'data_publicacao', 'data_inicio', 'data_fim', 'cpf_autoridade', 'valor', 'cnpj_envio'];
            }
            linhas.forEach(linha => {
                if (linha.trim() === '') return;
                linhasAdicionadas++;
                
                const campos = linha.split('\t');
                const tr = document.createElement('tr');
                headers.forEach((_, index) => {
                    const td = document.createElement('td');
                    td.textContent = campos[index] || '';
                    tr.appendChild(td);
                });
                // Adicionar botão de excluir
                const tdAcoes = document.createElement('td');
                tdAcoes.innerHTML = `<button class=\"delete-btn\" onclick=\"excluirLinha(this, '${secao}')\">Excluir</button>`;
                tr.appendChild(tdAcoes);
                tbody.appendChild(tr);
            });
            
            // Atualiza o contador de linhas, se houver linhas adicionadas
            if (linhasAdicionadas > 0) {
                const rowCount = document.getElementById(`count-${secao}`);
                if (rowCount) {
                    const currentCount = parseInt(rowCount.textContent || "0");
                    rowCount.textContent = currentCount + linhasAdicionadas;
                }
            }
            
            textarea.value = '';
            verificarDados();
        }

        function excluirLinha(button, secao) {
            button.closest('tr').remove();
            verificarDados();
        }

        function limparTodosOsDados() {
            // Limpar seções regulares
            ['1', '2', '3', '4'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    while (tbody.firstChild) {
                        tbody.removeChild(tbody.firstChild);
                    }
                }
            });
            
            // Limpar seções de alteração
            ['alteracao1', 'alteracao2'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    while (tbody.firstChild) {
                        tbody.removeChild(tbody.firstChild);
                    }
                }
            });
        }

        function carregarDadosParaSecaoRegular(secaoID, linhas) {
            const tbody = document.getElementById(`dados-body-${secaoID}`);
            if (!tbody) return;
            
            const headers = ['cnpj_ug', 'id_contrato', 'id_contrato_pncp', 'cnpj_procedimento', 'id_contratacao', 'numero_contrato', 'ano_contrato', 'cpf_cnpj', 'numero_processo', 'ano_processo', 'objeto', 'data_assinatura', 'data_publicacao', 'data_inicio', 'data_fim', 'cpf_autoridade', 'valor', 'cnpj_envio'];
            
            linhas.forEach(linha => {
                const tr = document.createElement('tr');
                
                // Adicionar células com os dados
                headers.forEach(header => {
                    const td = document.createElement('td');
                    td.textContent = linha[header] || '';
                    tr.appendChild(td);
                });
                
                // Adicionar botão de excluir
                const tdAcoes = document.createElement('td');
                tdAcoes.innerHTML = `<button class="delete-btn" onclick="excluirLinha(this, '${secaoID}')">Excluir</button>`;
                tr.appendChild(tdAcoes);
                
                tbody.appendChild(tr);
            });
            
            // Atualizar contador
            const rowCount = document.getElementById(`count-${secaoID}`);
            if (rowCount) {
                rowCount.textContent = linhas.length;
            }
        }
        
        function carregarDadosParaSecaoAlteracao(secaoID, linhas) {
            const tbody = document.getElementById(`dados-body-${secaoID}`);
            if (!tbody) return;
            
            const headers = ['cnpj_contratante', 'id_contrato', 'tipo_termo', 'numero_termo', 'ano_termo', 'contratado', 'numero_processo', 'ano_processo', 'objeto', 'data_assinatura', 'data_publicacao', 'data_inicio', 'data_fim', 'cpf_autoridade', 'valor', 'cnpj_envio'];
            
            linhas.forEach(linha => {
                const tr = document.createElement('tr');
                
                // Adicionar células com os dados
                headers.forEach(header => {
                    const td = document.createElement('td');
                    td.textContent = linha[header] || '';
                    tr.appendChild(td);
                });
                
                // Adicionar botão de excluir
                const tdAcoes = document.createElement('td');
                tdAcoes.innerHTML = `<button class="delete-btn" onclick="excluirLinha(this, '${secaoID}')">Excluir</button>`;
                tr.appendChild(tdAcoes);
                
                tbody.appendChild(tr);
            });
            
            // Atualizar contador
            const rowCount = document.getElementById(`count-${secaoID}`);
            if (rowCount) {
                rowCount.textContent = linhas.length;
            }
        }

        function downloadJSON() {
            // Coletar todos os dados das tabelas
            const dados = {
                secoes: {
                    cpf_cnpj: [], 
                    data_assinatura: [],
                    documento_comprobatorio: [],
                    integridade_referencial: [],
                    alteracao_documento: [],
                    alteracao_integridade: []
                }
            };

            // Função auxiliar para extrair dados de uma linha da tabela
            function extrairDadosLinha(tr, headers) {
                const linha = {};
                tr.querySelectorAll('td').forEach((td, index) => {
                    if (index < headers.length) {
                        linha[headers[index]] = td.textContent.trim();
                    }
                });
                return linha;
            }

            // Coletar dados das seções regulares
            const headersRegulares = ['cnpj_ug', 'id_contrato', 'id_contrato_pncp', 'cnpj_procedimento',
                           'id_contratacao', 'numero_contrato', 'ano_contrato', 'cpf_cnpj',
                           'numero_processo', 'ano_processo', 'objeto', 'data_assinatura',
                           'data_publicacao', 'data_inicio', 'data_fim', 'cpf_autoridade',
                           'valor', 'cnpj_envio'];
            const secoes = [
                {id: '1', key: 'cpf_cnpj'},
                {id: '2', key: 'data_assinatura'},
                {id: '3', key: 'documento_comprobatorio'},
                {id: '4', key: 'integridade_referencial'}
            ];
            secoes.forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao.id}`);
                const linhas = tbody.querySelectorAll('tr:not(.sem-dados-msg)');
                linhas.forEach(tr => {
                    const dadosLinha = extrairDadosLinha(tr, headersRegulares);
                    dados.secoes[secao.key].push(dadosLinha);
                });
            });
            
            // Coletar dados das seções de alteração
            const headersAlteracao = ['cnpj_contratante', 'id_contrato', 'tipo_termo', 'numero_termo', 
                                 'ano_termo', 'contratado', 'numero_processo', 'ano_processo', 
                                 'objeto', 'data_assinatura', 'data_publicacao', 'data_inicio', 
                                 'data_fim', 'cpf_autoridade', 'valor', 'cnpj_envio'];
            const secoesAlteracao = [
                {id: 'alteracao1', key: 'alteracao_documento'},
                {id: 'alteracao2', key: 'alteracao_integridade'}
            ];
            secoesAlteracao.forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao.id}`);
                const linhas = tbody.querySelectorAll('tr:not(.sem-dados-msg)');
                linhas.forEach(tr => {
                    const dadosLinha = extrairDadosLinha(tr, headersAlteracao);
                    dados.secoes[secao.key].push(dadosLinha);
                });
            });

            // Adicionar informações do cabeçalho
            dados.municipio = "SAO LUIS";
            dados.cnpj = "06307102000130";
            dados.exercicio = "2025";
            dados.data_exportacao = new Date().toISOString();

            // Criar e fazer download do arquivo JSON
            const jsonStr = JSON.stringify(dados, null, 2);
            const blob = new Blob([jsonStr], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'dados_contratos_2025.json';
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
        }

        function toggleInputSection(secao) {
            const inputSection = document.getElementById(`input-section-${secao}`);
            const button = inputSection.previousElementSibling;
            
            if (inputSection.classList.contains('visible')) {
                inputSection.classList.remove('visible');
                button.textContent = 'Adicionar Dados';
            } else {
                inputSection.classList.add('visible');
                button.textContent = 'Ocultar Área de Dados';
            }
        }

        function baixarPDF() {
            const opt = {
                margin: 0,
                filename: 'detalhes_contratos_2025.pdf',
                image: { type: 'jpeg', quality: 0.98 },
                html2canvas: { scale: 2 },
                jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };
            html2pdf().set(opt).from(document.body).save();
        }

        function toggleAccordion(secao, el) {
            const details = document.getElementById('accordion-details-' + secao);
            if (details.classList.contains('open')) {
                details.classList.remove('open');
                el.classList.remove('open');
            } else {
                details.classList.add('open');
                el.classList.add('open');
            }
            
            // Atualizar o ícone da seta
            const arrow = el.querySelector('.accordion-arrow');
            if (arrow) {
                arrow.textContent = details.classList.contains('open') ? '▼' : '▶';
            }
        }

        function verificarDados() {
            ['1', '2', '3', '4', 'alteracao1', 'alteracao2'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                const accordionError = document.querySelector(`[onclick="toggleAccordion('${secao}', this)"]`);
                const rowCount = document.getElementById(`count-${secao}`);
                
                if (tbody) {
                    const rows = tbody.querySelectorAll('tr:not(.sem-dados-msg)').length;
                    
                    // Atualiza o contador de linhas
                    if (rowCount) {
                        rowCount.textContent = rows;
                    }
                    
                    if (rows === 0) {
                        const semDadosMsg = document.createElement('tr');
                        semDadosMsg.className = 'sem-dados-msg';
                        semDadosMsg.innerHTML = `<td colspan="19" style="text-align: center; padding: 15px; font-style: italic; color: #6c757d;">
                            AVISO: O sistema https://app.tcema.tc.br/sinccontrata/relatorioAchadosSistema está sobrecarregado de informações.
                        </td>`;
                        
                        // Remove mensagem existente, se houver
                        tbody.querySelectorAll('.sem-dados-msg').forEach(msg => msg.remove());
                        
                        // Adiciona nova mensagem
                        tbody.appendChild(semDadosMsg);
                        
                        // Adiciona classe sem-dados ao accordion
                        if (accordionError) {
                            accordionError.classList.add('sem-dados');
                        }
                    } else {
                        // Remove mensagem se existir e houver dados
                        tbody.querySelectorAll('.sem-dados-msg').forEach(msg => msg.remove());
                        
                        // Remove classe sem-dados do accordion
                        if (accordionError) {
                            accordionError.classList.remove('sem-dados');
                        }
                    }
                }
            });
        }

        function carregarCNPJsDisponiveis() {
            // Para CNPJ UG (seções 1-4)
            const cnpjsUG = new Set();
            ['1', '2', '3', '4'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        const cnpjCell = tr.querySelector('td:first-child');
                        if (cnpjCell && cnpjCell.textContent.trim()) {
                            cnpjsUG.add(cnpjCell.textContent.trim());
                        }
                    });
                }
            });
            
            // Para CNPJ Contratante (seções alteracao1-2)
            const cnpjsContratante = new Set();
            ['alteracao1', 'alteracao2'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        const cnpjCell = tr.querySelector('td:first-child');
                        if (cnpjCell && cnpjCell.textContent.trim()) {
                            cnpjsContratante.add(cnpjCell.textContent.trim());
                        }
                    });
                }
            });
            
            // Se tiver mais de um CNPJ UG, exibir o filtro
            if (cnpjsUG.size > 1) {
                const container = document.getElementById('filtro-cnpj-ug-container');
                if (container) {
                    container.style.display = 'flex';
                }
                
                // Preencher o dropdown
                const select = document.getElementById('filtro-cnpj-ug');
                select.innerHTML = '<option value="">Todos os CNPJs UG</option>';
                
                // Ordenar CNPJs para melhor navegação
                const cnpjsOrdenados = Array.from(cnpjsUG).sort();
                
                cnpjsOrdenados.forEach(cnpj => {
                    const option = document.createElement('option');
                    option.value = cnpj;
                    option.textContent = cnpj;
                    select.appendChild(option);
                });
            }
            
            // Se tiver mais de um CNPJ Contratante, exibir o filtro
            if (cnpjsContratante.size > 1) {
                const container = document.getElementById('filtro-cnpj-contratante-container');
                if (container) {
                    container.style.display = 'flex';
                }
                
                // Preencher o dropdown
                const select = document.getElementById('filtro-cnpj-contratante');
                select.innerHTML = '<option value="">Todos os CNPJs Contratantes</option>';
                
                // Ordenar CNPJs para melhor navegação
                const cnpjsOrdenados = Array.from(cnpjsContratante).sort();
                
                cnpjsOrdenados.forEach(cnpj => {
                    const option = document.createElement('option');
                    option.value = cnpj;
                    option.textContent = cnpj;
                    select.appendChild(option);
                });
            }
        }
        
        function filtrarPorCNPJUG() {
            const cnpjSelecionado = document.getElementById('filtro-cnpj-ug').value;
            
            // Se nenhum CNPJ selecionado, mostrar tudo
            if (!cnpjSelecionado) {
                resetarFiltroCNPJUG();
                return;
            }
            
            // Filtrar linhas nas seções regulares (1-4)
            ['1', '2', '3', '4'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        const cnpjCell = tr.querySelector('td:first-child');
                        if (cnpjCell) {
                            if (cnpjCell.textContent.trim() === cnpjSelecionado) {
                                tr.style.display = '';
                            } else {
                                tr.style.display = 'none';
                            }
                        }
                    });
                }
            });
            
            // Atualizar contadores visíveis
            atualizarContadoresVisiveis(['1', '2', '3', '4']);
        }
        
        function filtrarPorCNPJContratante() {
            const cnpjSelecionado = document.getElementById('filtro-cnpj-contratante').value;
            
            // Se nenhum CNPJ selecionado, mostrar tudo
            if (!cnpjSelecionado) {
                resetarFiltroCNPJContratante();
                return;
            }
            
            // Filtrar linhas nas seções de alteração
            ['alteracao1', 'alteracao2'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        const cnpjCell = tr.querySelector('td:first-child');
                        if (cnpjCell) {
                            if (cnpjCell.textContent.trim() === cnpjSelecionado) {
                                tr.style.display = '';
                            } else {
                                tr.style.display = 'none';
                            }
                        }
                    });
                }
            });
            
            // Atualizar contadores visíveis
            atualizarContadoresVisiveis(['alteracao1', 'alteracao2']);
        }
        
        function resetarFiltroCNPJUG() {
            // Resetar o dropdown
            document.getElementById('filtro-cnpj-ug').value = '';
            
            // Mostrar todas as linhas nas seções
            ['1', '2', '3', '4'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        tr.style.display = '';
                    });
                }
            });
            
            // Atualizar contadores
            atualizarContadoresVisiveis(['1', '2', '3', '4']);
        }
        
        function resetarFiltroCNPJContratante() {
            // Resetar o dropdown
            document.getElementById('filtro-cnpj-contratante').value = '';
            
            // Mostrar todas as linhas nas seções
            ['alteracao1', 'alteracao2'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        tr.style.display = '';
                    });
                }
            });
            
            // Atualizar contadores
            atualizarContadoresVisiveis(['alteracao1', 'alteracao2']);
        }
        
        function atualizarContadoresVisiveis(secoes) {
            secoes.forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                const rowCount = document.getElementById(`count-${secao}`);
                
                if (tbody && rowCount) {
                    // Contar apenas linhas visíveis
                    const visibleRows = tbody.querySelectorAll('tr:not(.sem-dados-msg):not([style*="display: none"])').length;
                    rowCount.textContent = visibleRows;
                    
                    // Atualizar classe sem-dados se necessário
                    const accordionError = document.querySelector(`[onclick="toggleAccordion('${secao}', this)"]`);
                    if (accordionError) {
                        if (visibleRows === 0) {
                            accordionError.classList.add('sem-dados');
                        } else {
                            accordionError.classList.remove('sem-dados');
                        }
                    }
                }
            });
        }

        function importarJSON(event) {
            const file = event.target.files[0];
            if (!file) return;
            
            // Mostrar indicador de carregamento
            const loadingMsg = document.createElement('div');
            loadingMsg.id = 'loading-message';
            loadingMsg.innerHTML = '<div style="position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.7); z-index: 9999; display: flex; justify-content: center; align-items: center;"><div style="background: white; padding: 20px; border-radius: 8px; text-align: center;"><i class="fas fa-spinner fa-spin" style="font-size: 2em; margin-bottom: 10px; color: var(--primary-color);"></i><p>Carregando dados...</p></div></div>';
            document.body.appendChild(loadingMsg);
            
            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const dados = JSON.parse(e.target.result);
                    
                    // Limpar dados atuais
                    limparTodosOsDados();
                    
                    // Processar os dados por seção
                    if (dados.secoes) {
                        // Mapear seções regulares (1-4)
                        const secoesRegulares = ['1', '2', '3', '4'];
                        const chaveSecoesRegulares = [
                            'cpf_cnpj', 
                            'data_assinatura',
                            'documento_comprobatorio',
                            'integridade_referencial'
                        ];
                        
                        // Processar seções regulares
                        secoesRegulares.forEach((secaoID, index) => {
                            const chave = chaveSecoesRegulares[index];
                            if (dados.secoes[chave] && Array.isArray(dados.secoes[chave]) && dados.secoes[chave].length > 0) {
                                carregarDadosParaSecaoRegular(secaoID, dados.secoes[chave]);
                            }
                        });
                        
                        // Processar seções de alteração
                        const secoesAlteracao = ['alteracao1', 'alteracao2'];
                        const chaveSecoesAlteracao = [
                            'alteracao_documento',
                            'alteracao_integridade'
                        ];
                        
                        secoesAlteracao.forEach((secaoID, index) => {
                            const chave = chaveSecoesAlteracao[index];
                            if (dados.secoes[chave] && Array.isArray(dados.secoes[chave]) && dados.secoes[chave].length > 0) {
                                carregarDadosParaSecaoAlteracao(secaoID, dados.secoes[chave]);
                            }
                        });
                    }
                    
                    // Atualizar contadores e exibição
                    verificarDados();
                    setTimeout(carregarCNPJsDisponiveis, 100);
                    
                    // Mostrar mensagem de sucesso
                    const msgSucesso = document.createElement('div');
                    msgSucesso.style.cssText = 'position: fixed; top: 20px; right: 20px; background: var(--success-color); color: white; padding: 15px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); z-index: 1000; animation: fadeOut 5s forwards;';
                    msgSucesso.innerHTML = '<i class="fas fa-check-circle" style="margin-right: 8px;"></i> Dados importados com sucesso!';
                    document.body.appendChild(msgSucesso);
                    
                    // Adicionar animação de fadeOut
                    const style = document.createElement('style');
                    style.textContent = '@keyframes fadeOut { 0% { opacity: 1; } 70% { opacity: 1; } 100% { opacity: 0; display: none; } }';
                    document.head.appendChild(style);
                    
                    setTimeout(() => {
                        document.body.removeChild(msgSucesso);
                        document.head.removeChild(style);
                    }, 5000);
                } catch (error) {
                    console.error('Erro ao processar JSON:', error);
                    alert('Erro ao processar o arquivo JSON. Verifique se o formato está correto.');
                }
                
                // Remover indicador de carregamento
                const loadingMsg = document.getElementById('loading-message');
                if (loadingMsg) {
                    document.body.removeChild(loadingMsg);
                }
                
                // Limpar input de arquivo para permitir carregar o mesmo arquivo novamente
                event.target.value = '';
            };
            
            reader.onerror = function() {
                alert('Erro ao ler o arquivo.');
                const loadingMsg = document.getElementById('loading-message');
                if (loadingMsg) {
                    document.body.removeChild(loadingMsg);
                }
                event.target.value = '';
            };
            
            reader.readAsText(file);
        }

        function carregarDadosJSON() {
            // Mostrar indicador de carregamento
            const loadingMsg = document.createElement('div');
            loadingMsg.id = 'loading-message';
            loadingMsg.innerHTML = '<div style="position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.7); z-index: 9999; display: flex; justify-content: center; align-items: center;"><div style="background: white; padding: 20px; border-radius: 8px; text-align: center;"><i class="fas fa-spinner fa-spin" style="font-size: 2em; margin-bottom: 10px; color: var(--primary-color);"></i><p>Carregando dados...</p></div></div>';
            document.body.appendChild(loadingMsg);
            
            // URL do JSON fixo para carregar do GitHub
            const jsonUrl = 'https://raw.githubusercontent.com/Taskymaster/meu-repositorio-json/refs/heads/main/dados_contratos_2025.md';
            
            fetch(jsonUrl)
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Erro ao buscar os dados: ' + response.status);
                    }
                    return response.text(); // Carrega como texto em vez de JSON
                })
                .then(textData => {
                    // Converter o texto para objeto JSON
                    try {
                        const dados = JSON.parse(textData);
                        
                        // Limpar dados atuais
                        limparTodosOsDados();
                        
                        // Processar os dados por seção
                        if (dados.secoes) {
                            // Mapear seções regulares (1-4)
                            const secoesRegulares = ['1', '2', '3', '4'];
                            const chaveSecoesRegulares = [
                                'cpf_cnpj', 
                                'data_assinatura',
                                'documento_comprobatorio',
                                'integridade_referencial'
                            ];
                            
                            // Processar seções regulares
                            secoesRegulares.forEach((secaoID, index) => {
                                const chave = chaveSecoesRegulares[index];
                                if (dados.secoes[chave] && Array.isArray(dados.secoes[chave]) && dados.secoes[chave].length > 0) {
                                    carregarDadosParaSecaoRegular(secaoID, dados.secoes[chave]);
                                }
                            });
                            
                            // Processar seções de alteração
                            const secoesAlteracao = ['alteracao1', 'alteracao2'];
                            const chaveSecoesAlteracao = [
                                'alteracao_documento',
                                'alteracao_integridade'
                            ];
                            
                            secoesAlteracao.forEach((secaoID, index) => {
                                const chave = chaveSecoesAlteracao[index];
                                if (dados.secoes[chave] && Array.isArray(dados.secoes[chave]) && dados.secoes[chave].length > 0) {
                                    carregarDadosParaSecaoAlteracao(secaoID, dados.secoes[chave]);
                                }
                            });
                        }
                        
                        // Atualizar contadores e exibição
                        verificarDados();
                        setTimeout(carregarCNPJsDisponiveis, 100);
                        
                        // Mostrar mensagem de sucesso
                        const msgSucesso = document.createElement('div');
                        msgSucesso.style.cssText = 'position: fixed; top: 20px; right: 20px; background: var(--success-color); color: white; padding: 15px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); z-index: 1000; animation: fadeOut 5s forwards;';
                        msgSucesso.innerHTML = '<i class="fas fa-check-circle" style="margin-right: 8px;"></i> Dados carregados com sucesso!';
                        document.body.appendChild(msgSucesso);
                        
                        // Adicionar animação de fadeOut
                        const style = document.createElement('style');
                        style.textContent = '@keyframes fadeOut { 0% { opacity: 1; } 70% { opacity: 1; } 100% { opacity: 0; display: none; } }';
                        document.head.appendChild(style);
                        
                        setTimeout(() => {
                            if (document.body.contains(msgSucesso)) {
                                document.body.removeChild(msgSucesso);
                            }
                            if (document.head.contains(style)) {
                                document.head.removeChild(style);
                            }
                        }, 5000);
                    } catch (parseError) {
                        console.error('Erro ao fazer parse dos dados:', parseError);
                        alert('Erro ao processar o arquivo: ' + parseError.message);
                    }
                })
                .catch(error => {
                    console.error('Erro ao processar arquivo:', error);
                    alert('Erro ao processar o arquivo: ' + error.message);
                })
                .finally(() => {
                    // Remover indicador de carregamento
                    const loadingMsg = document.getElementById('loading-message');
                    if (loadingMsg) {
                        document.body.removeChild(loadingMsg);
                    }
                });
        }

        window.onload = function() {
            // Verificar se há dados nas tabelas
            verificarDados();
            
            // Inicializar o sistema de filtragem
            setTimeout(carregarCNPJsDisponiveis, 100);
            
            // Carregar dados automaticamente do GitHub
            carregarDadosJSON();
        };
    </script>
</body>
</html> 
