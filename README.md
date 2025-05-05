<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gestão de Contratos 2024 | SINC Contratações</title>
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
        .error-message {
            padding: 15px;
            border-radius: 5px;
            margin: 10px 0;
            text-align: center;
            margin-bottom: 30px;
            font-weight: bold;
            font-size: 1.1em;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            background-color: #f8d7da;
            color: #721c24;
            border-left: 5px solid #dc3545;
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
            background-color: white;
            padding: 15px;
            margin: 20px 0;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: none;
        }
        .input-section.visible {
            display: block;
        }
        .toggle-input-btn {
            background-color: var(--secondary-color);
            color: white;
            padding: 8px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin-bottom: 10px;
        }
        .toggle-input-btn:hover {
            background-color: var(--accent-color);
        }
        .input-section textarea {
            width: 100%;
            height: 100px;
            margin: 10px 0;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-family: monospace;
        }
        .horizontal-scroll {
            overflow-x: auto;
            white-space: nowrap;
            padding: 20px 0;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            margin-top: 20px;
        }
        .data-grid {
            min-width: 100%;
            border-collapse: collapse;
        }
        .data-grid th {
            background-color: #f8f9fa;
            padding: 12px;
            text-align: left;
            font-weight: bold;
            border-bottom: 2px solid #dee2e6;
            white-space: nowrap;
        }
        .data-grid td {
            padding: 12px;
            border-bottom: 1px solid #dee2e6;
            white-space: nowrap;
        }
        .actions {
            text-align: center;
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 10px;
        }
        .save-btn, .process-btn {
            background-color: var(--success-color);
            color: white;
            padding: 8px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .back-btn {
            background-color: var(--primary-color);
            color: white;
            padding: 8px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
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
            padding: 8px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
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
        .tabela-sem-dados {
            background-color: #f8f9fa;
            padding: 15px;
            text-align: center;
            border-radius: 5px;
            margin: 10px 0;
            font-style: italic;
            color: #6c757d;
        }
        .filtro-cnpj {
            background-color: white;
            padding: 1.25rem;
            margin-bottom: 2rem;
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

        .section-title {
            color: var(--primary-color);
            margin: 2rem 0 1rem;
            font-size: 1.5rem;
            font-weight: 600;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h2>MUNICÍPIO DE SAO LUIS - CNPJ: 06307102000130 - EXERCÍCIO: 2024</h2>
            <h2>Layout: CONTRATO <span class="year-badge">2024</span></h2>
            <div class="actions">
                <button class="btn download-btn icon-btn" onclick="downloadJSON()"><i class="fas fa-download"></i> Baixar JSON</button>
                <button class="btn download-btn icon-btn" style="background-color: var(--info-color); cursor: pointer;" onclick="baixarPDF()"><i class="fas fa-file-pdf"></i> Baixar PDF</button>
                <button class="btn download-btn icon-btn" style="background-color: var(--success-color); cursor: pointer;" onclick="carregarDadosJSON()"><i class="fas fa-cloud-download-alt"></i> Carregar do GitHub</button>
                <a href="dashboard.html" class="btn back-btn icon-btn"><i class="fas fa-arrow-left"></i> Voltar ao Painel</a>
            </div>
        </div>

        <!-- Filtro por CNPJ Contratante - aparece apenas quando há mais de um CNPJ -->
        <div id="filtro-cnpj-container" class="filtro-cnpj" style="display: none;">
            <label for="filtro-cnpj-contratante"><i class="fas fa-filter"></i> Filtrar por CNPJ Contratante:</label>
            <select id="filtro-cnpj-contratante" onchange="filtrarPorCNPJ()">
                <option value="">Todos os CNPJs</option>
            </select>
            <button class="reset-btn icon-btn" onclick="resetarFiltro()"><i class="fas fa-times"></i> Limpar Filtro</button>
        </div>

        <h3 class="section-title">Contratos com Pendências - Exercício 2024</h3>

        <!-- Primeira Seção - Data Assinatura -->
        <div class="accordion-error" onclick="toggleAccordion('1', this)">
            <span><i class="fas fa-calendar-alt"></i> ERRO! A 'data_assinatura' não pode ser superior à 'data_inicio' <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-1">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-1">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('1')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-1">
                <textarea id="input-dados-1" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('1')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-1"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Segunda Seção - Data Inválida -->
        <div class="accordion-error" onclick="toggleAccordion('2', this)">
            <span><i class="fas fa-exclamation-triangle"></i> ERRO! A data da assinatura é inválida <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-2">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-2">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('2')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-2">
                <textarea id="input-dados-2" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('2')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-2"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Terceira Seção - Data Início -->
        <div class="accordion-error" onclick="toggleAccordion('3', this)">
            <span><i class="fas fa-calendar-times"></i> ERRO! A 'data_inicio' não pode ser superior à 'data_fim' <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-3">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-3">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('3')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-3">
                <textarea id="input-dados-3" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('3')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-3"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Quarta Seção - CPF/CNPJ Contratado -->
        <div class="accordion-error" onclick="toggleAccordion('4', this)">
            <span><i class="fas fa-id-card"></i> ERRO! O código do CPF/CNPJ informado para 'contratado' é inválido <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-4">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-4">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('4')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-4">
                <textarea id="input-dados-4" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('4')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-4"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Quinta Seção - Integridade Referencial -->
        <div class="accordion-error" onclick="toggleAccordion('5', this)">
            <span><i class="fas fa-link"></i> ERRO DE INTEGRIDADE REFERENCIAL! O 'id_procedimento' não tem correspondente no layout PROCEDIMENTO_LICITATORIO, PROCEDIMENTO_CONTRATACAO ou PROCEDIMENTO_ADESAO <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-5">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-5">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('5')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-5">
                <textarea id="input-dados-5" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('5')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-5"></tbody>
                </table>
            </div>
        </div>

        <div class="actions">
            <button class="back-btn" onclick="window.history.back()">Voltar</button>
        </div>

        <div class="section-divider"></div>
        <div class="header">
            <h2>Layout: ALTERACAO_CONTRATUAL</h2>
        </div>

        <!-- Seção de Alteração - Data Assinatura -->
        <div class="accordion-error" onclick="toggleAccordion('6', this)">
            <span><i class="fas fa-calendar-alt"></i> ERRO! A 'data_assinatura' não pode ser superior à 'data_publicacao' <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-6">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-6">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('6')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-6">
                <textarea id="input-dados-6" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('6')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-6"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Seção de Alteração - Informação Obrigatória -->
        <div class="accordion-error" onclick="toggleAccordion('7', this)">
            <span><i class="fas fa-exclamation-circle"></i> ERRO! Informação obrigatória não inserida <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-7">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-7">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('7')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-7">
                <textarea id="input-dados-7" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('7')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-7"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Seção de Alteração - Integridade Referencial -->
        <div class="accordion-error" onclick="toggleAccordion('8', this)">
            <span><i class="fas fa-link-slash"></i> ERRO DE INTEGRIDADE REFERENCIAL! O 'id_contrato' não tem correspondente no layout CONTRATO. <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-8">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-8">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('8')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-8">
                <textarea id="input-dados-8" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('8')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-8"></tbody>
                </table>
            </div>
        </div>

        <div class="section-divider"></div>

        <!-- Seção de Alteração - Documento Comprobatório -->
        <div class="accordion-error" onclick="toggleAccordion('9', this)">
            <span><i class="fas fa-file-alt"></i> ERRO! Documento comprobatório não apresentado <span style="font-weight:normal;font-size:0.9em;">(clique para exibir/ocultar detalhes)</span> <span class="row-count" id="count-9">0</span></span>
            <span class="accordion-arrow">▶</span>
        </div>
        <div class="accordion-details" id="accordion-details-9">
            <button class="btn toggle-input-btn icon-btn" onclick="toggleInputSection('9')"><i class="fas fa-plus-circle"></i> Adicionar Dados</button>
            <div class="input-section" id="input-section-9">
                <textarea id="input-dados-9" placeholder="Cole aqui os dados no formato:&#10;cnpj_contratante    id_contrato    tipo_termo    numero_termo    ano_termo    contratado    numero_processo    ano_processo    objeto    data_assinatura    data_publicacao    data_inicio    data_fim    cpf_autoridade    valor    cnpj_envio"></textarea>
                <div class="actions">
                    <button class="btn process-btn icon-btn" onclick="processarDados('9')"><i class="fas fa-check-circle"></i> Processar Dados</button>
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
                    <tbody id="dados-body-9"></tbody>
                </table>
            </div>
        </div>

        <div class="actions">
            <a href="dashboard.html" class="btn back-btn icon-btn"><i class="fas fa-arrow-left"></i> Voltar ao Painel</a>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <script>
        function processarDados(secao) {
            const textarea = document.getElementById(`input-dados-${secao}`);
            const tbody = document.getElementById(`dados-body-${secao}`);
            const linhas = textarea.value.trim().split('\n');
            const headers = ['cnpj_contratante', 'id_contrato', 'tipo_termo', 'numero_termo', 'ano_termo', 'contratado', 'numero_processo', 'ano_processo', 'objeto', 'data_assinatura', 'data_publicacao', 'data_inicio', 'data_fim', 'cpf_autoridade', 'valor', 'cnpj_envio'];
            
            // Contador para linhas adicionadas
            let linhasAdicionadas = 0;
            
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
                tdAcoes.innerHTML = `<button class="delete-btn" onclick="excluirLinha(this, '${secao}')">Excluir</button>`;
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
            ['1','2','3','4','5','6','7','8','9'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    while (tbody.firstChild) {
                        tbody.removeChild(tbody.firstChild);
                    }
                }
            });
        }

        // Função para carregar dados do arquivo JSON
        function carregarDadosJSON() {
            // Mostrar indicador de carregamento
            const loadingMsg = document.createElement('div');
            loadingMsg.id = 'loading-message';
            loadingMsg.innerHTML = '<div style="position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.7); z-index: 9999; display: flex; justify-content: center; align-items: center;"><div style="background: white; padding: 20px; border-radius: 8px; text-align: center;"><i class="fas fa-spinner fa-spin" style="font-size: 2em; margin-bottom: 10px; color: var(--primary-color);"></i><p>Carregando dados...</p></div></div>';
            document.body.appendChild(loadingMsg);
            
            // URL do JSON fixo (substitua pela URL real)
            const jsonUrl = 'https://raw.githubusercontent.com/Taskymaster/meu-repositorio-json/refs/heads/main/dados_contratos_2024.md';
            
            fetch(jsonUrl)
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Erro ao buscar os dados: ' + response.status);
                    }
                    return response.text(); // Alterado para text() em vez de json() já que o conteúdo é .md
                })
                .then(textData => {
                    // Converter o texto para objeto JSON
                    try {
                        const dados = JSON.parse(textData);
                        
                        // Limpar dados atuais
                        limparTodosOsDados();
                        
                        // Processar os dados por seção
                        if (dados.secoes) {
                            // Mapear chaves do JSON para seções do HTML
                            const mapeamentoSecoes = {
                                'erro_data_assinatura': '1',
                                'erro_data_invalida': '2',
                                'erro_data_inicio': '3',
                                'erro_cpf_cnpj': '4',
                                'erro_integridade': '5',
                                'erro_alteracao_data': '6',
                                'erro_informacao_obrigatoria': '7',
                                'erro_alteracao_integridade': '8',
                                'erro_documento': '9'
                            };
                            
                            // Processar os dados por seção
                            Object.entries(dados.secoes).forEach(([chaveSecao, linhas]) => {
                                const secaoID = mapeamentoSecoes[chaveSecao];
                                if (secaoID && Array.isArray(linhas) && linhas.length > 0) {
                                    console.log(`Carregando ${linhas.length} linhas para a seção ${secaoID} de ${chaveSecao}`);
                                    carregarDadosParaSecao(secaoID, linhas);
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
            // Carregar dados automaticamente do endpoint
            carregarDadosJSON();
        };

        function toggleInputSection(secao) {
            const inputSection = document.getElementById(`input-section-${secao}`);
            const button = inputSection.previousElementSibling;
            
            if (inputSection.classList.contains('visible')) {
                inputSection.classList.remove('visible');
                button.innerHTML = '<i class="fas fa-plus-circle"></i> Adicionar Dados';
            } else {
                inputSection.classList.add('visible');
                button.innerHTML = '<i class="fas fa-minus-circle"></i> Ocultar Área de Dados';
            }
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
            ['1','2','3','4','5','6','7','8','9'].forEach(secao => {
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
                        semDadosMsg.innerHTML = `<td colspan="17" style="text-align: center; padding: 15px; font-style: italic; color: #6c757d;">
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
            const cnpjs = new Set();
            
            // Coletar CNPJs de todas as seções
            ['1','2','3','4','5','6','7','8','9'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        const cnpjCell = tr.querySelector('td:first-child');
                        if (cnpjCell && cnpjCell.textContent.trim()) {
                            cnpjs.add(cnpjCell.textContent.trim());
                        }
                    });
                }
            });
            
            // Se tiver mais de um CNPJ, exibir o filtro
            if (cnpjs.size > 1) {
                const container = document.getElementById('filtro-cnpj-container');
                if (container) {
                    container.style.display = 'flex';
                }
                
                // Preencher o dropdown
                const select = document.getElementById('filtro-cnpj-contratante');
                select.innerHTML = '<option value="">Todos os CNPJs</option>';
                
                // Ordenar CNPJs para melhor navegação
                const cnpjsOrdenados = Array.from(cnpjs).sort();
                
                cnpjsOrdenados.forEach(cnpj => {
                    const option = document.createElement('option');
                    option.value = cnpj;
                    option.textContent = cnpj;
                    select.appendChild(option);
                });
            }
        }
        
        function filtrarPorCNPJ() {
            const cnpjSelecionado = document.getElementById('filtro-cnpj-contratante').value;
            
            // Se nenhum CNPJ selecionado, mostrar tudo
            if (!cnpjSelecionado) {
                resetarFiltro();
                return;
            }
            
            // Filtrar linhas em todas as seções
            ['1','2','3','4','5','6','7','8','9'].forEach(secao => {
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
            atualizarContadoresVisiveis();
        }
        
        function resetarFiltro() {
            // Resetar o dropdown
            document.getElementById('filtro-cnpj-contratante').value = '';
            
            // Mostrar todas as linhas nas seções
            ['1','2','3','4','5','6','7','8','9'].forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao}`);
                if (tbody) {
                    tbody.querySelectorAll('tr:not(.sem-dados-msg)').forEach(tr => {
                        tr.style.display = '';
                    });
                }
            });
            
            // Atualizar contadores
            verificarDados();
        }
        
        function atualizarContadoresVisiveis() {
            ['1','2','3','4','5','6','7','8','9'].forEach(secao => {
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

        function carregarDadosParaSecao(secaoID, linhas) {
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
            const dados = { secoes: {} };
            const headers = ['cnpj_contratante', 'id_contrato', 'tipo_termo', 'numero_termo', 'ano_termo', 'contratado', 'numero_processo', 'ano_processo', 'objeto', 'data_assinatura', 'data_publicacao', 'data_inicio', 'data_fim', 'cpf_autoridade', 'valor', 'cnpj_envio'];
            
            const secoes = [
                {id: '1', key: 'erro_data_assinatura'},
                {id: '2', key: 'erro_data_invalida'},
                {id: '3', key: 'erro_data_inicio'},
                {id: '4', key: 'erro_cpf_cnpj'},
                {id: '5', key: 'erro_integridade'},
                {id: '6', key: 'erro_alteracao_data'},
                {id: '7', key: 'erro_informacao_obrigatoria'},
                {id: '8', key: 'erro_alteracao_integridade'},
                {id: '9', key: 'erro_documento'}
            ];
            
            secoes.forEach(secao => {
                const tbody = document.getElementById(`dados-body-${secao.id}`);
                const linhas = tbody.querySelectorAll('tr:not(.sem-dados-msg)');
                dados.secoes[secao.key] = [];
                
                linhas.forEach(tr => {
                    const linha = {};
                    tr.querySelectorAll('td').forEach((td, index) => {
                        if (index < headers.length) {
                            linha[headers[index]] = td.textContent.trim();
                        }
                    });
                    dados.secoes[secao.key].push(linha);
                });
            });
            
            dados.municipio = "SAO LUIS";
            dados.cnpj = "06307102000130";
            dados.exercicio = "2024";
            dados.data_exportacao = new Date().toISOString();
            const jsonStr = JSON.stringify(dados, null, 2);
            const blob = new Blob([jsonStr], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = 'dados_contratos_2024.json';
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
        }
        
        function baixarPDF() {
            const opt = {
                margin: 0,
                filename: 'detalhes_contratos_2024.pdf',
                image: { type: 'jpeg', quality: 0.98 },
                html2canvas: { scale: 2 },
                jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };
            html2pdf().set(opt).from(document.body).save();
        }
    </script>
</body>
</html> 
