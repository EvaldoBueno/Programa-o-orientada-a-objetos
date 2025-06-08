código em java de cadastro de clientes 

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class CadastroClientes {

    public static void main(String[] args) {
        JFrame frame = new JFrame("Cadastro de Clientes");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 400);
        
        // Painel principal
        JPanel panel = new JPanel();
        panel.setLayout(new GridLayout(10, 2));

        // Campos do formulário
        panel.add(new JLabel("Código:"));
        JTextField txtCodigo = new JTextField();
        panel.add(txtCodigo);

        panel.add(new JLabel("Nome:"));
        JTextField txtNome = new JTextField();
        panel.add(txtNome);

        panel.add(new JLabel("Endereço:"));
        JTextField txtEndereco = new JTextField();
        panel.add(txtEndereco);

        panel.add(new JLabel("Bairro:"));
        JTextField txtBairro = new JTextField();
        panel.add(txtBairro);

        panel.add(new JLabel("Cidade:"));
        JTextField txtCidade = new JTextField();
        panel.add(txtCidade);

        panel.add(new JLabel("Estado:"));
        String[] estados = {"SP", "RJ", "MG", "RS"}; // Exemplo de estados
        JComboBox<String> cbEstado = new JComboBox<>(estados);
        panel.add(cbEstado);

        panel.add(new JLabel("CEP:"));
        JTextField txtCep = new JTextField();
        panel.add(txtCep);

        panel.add(new JLabel("Telefone:"));
        JTextField txtTelefone = new JTextField();
        panel.add(txtTelefone);

        panel.add(new JLabel("Observações:"));
        JTextArea txtObservacoes = new JTextArea();
        panel.add(txtObservacoes);

        // Botões
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnNovo = new JButton("Novo");

        // Adicionando ações aos botões
        btnSalvar.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                // Implementação da lógica de salvar
                JOptionPane.showMessageDialog(frame, "Cadastro salvo!");
            }
        });

        // Adicionando botões ao painel
        panel.add(btnNovo);
        panel.add(btnSalvar);
        panel.add(btnAlterar);
        panel.add(btnExcluir);

        frame.add(panel);
        frame.setVisible(true);
    }
}
--------------------------------------------------------------------------------------------------------------------------------------
Código: Tela de Cadastro de Clientes (CadastroClientes.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroClientes extends JFrame {

    public CadastroClientes() {
        setTitle("Cadastro de Clientes");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(11, 2, 5, 5));

        JTextField txtCodigo = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtBairro = new JTextField();
        JTextField txtCidade = new JTextField();
        String[] estados = {"SP", "RJ", "MG", "RS"};
        JComboBox<String> cbEstado = new JComboBox<>(estados);
        JTextField txtCep = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("Código:")); panel.add(txtCodigo);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Bairro:")); panel.add(txtBairro);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("CEP:")); panel.add(txtCep);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtCodigo.setText("");
            txtNome.setText("");
            txtEndereco.setText("");
            txtBairro.setText("");
            txtCidade.setText("");
            cbEstado.setSelectedIndex(0);
            txtCep.setText("");
            txtTelefone.setText("");
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Cadastro salvo:\n"
                + "Código: " + txtCodigo.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "Endereço: " + txtEndereco.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Cadastro alterado com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este cadastro?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtCodigo.setText("");
                txtNome.setText("");
                txtEndereco.setText("");
                txtBairro.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtCep.setText("");
                txtTelefone.setText("");
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Cadastro excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "Cidade: " + txtCidade.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela();
            dispose();
        });

        panel.add(btnNovo);     panel.add(btnSalvar);
        panel.add(btnAlterar);  panel.add(btnExcluir);
        panel.add(btnRelatorio);panel.add(btnRetornar);

        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}
------------------------------------------------------------------------------------------------------------------------------
Código: Tela de Cadastro de Funcionários (CadastroFuncionarios.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroFuncionarios extends JFrame {

    public CadastroFuncionarios() {
        setTitle("Cadastro de Funcionários");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(10, 2, 5, 5));

        JTextField txtId = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtCargo = new JTextField();
        JTextField txtDepartamento = new JTextField();
        JTextField txtCpf = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextField txtEmail = new JTextField();
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("ID:")); panel.add(txtId);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("Cargo:")); panel.add(txtCargo);
        panel.add(new JLabel("Departamento:")); panel.add(txtDepartamento);
        panel.add(new JLabel("CPF:")); panel.add(txtCpf);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Email:")); panel.add(txtEmail);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtId.setText("");
            txtNome.setText("");
            txtCargo.setText("");
            txtDepartamento.setText("");
            txtCpf.setText("");
            txtTelefone.setText("");
            txtEmail.setText("");
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Funcionário salvo:\n"
                + "ID: " + txtId.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "Cargo: " + txtCargo.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Dados do funcionário alterados com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este funcionário?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtId.setText("");
                txtNome.setText("");
                txtCargo.setText("");
                txtDepartamento.setText("");
                txtCpf.setText("");
                txtTelefone.setText("");
                txtEmail.setText("");
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Funcionário excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "Cargo: " + txtCargo.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela(); // Volta para a tela Home
            dispose();
        });

        panel.add(btnNovo);      panel.add(btnSalvar);
        panel.add(btnAlterar);   panel.add(btnExcluir);
        panel.add(btnRelatorio); panel.add(btnRetornar);
Código: Cadastro de Fornecedores (CadastroFornecedores.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroFornecedores extends JFrame {

    public CadastroFornecedores() {
        setTitle("Cadastro de Fornecedores");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(10, 2, 5, 5));

        JTextField txtId = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtCnpj = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextField txtEmail = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtCidade = new JTextField();
        JComboBox<String> cbEstado = new JComboBox<>(new String[]{"SP", "RJ", "MG", "RS"});
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("ID:")); panel.add(txtId);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("CNPJ:")); panel.add(txtCnpj);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Email:")); panel.add(txtEmail);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtId.setText("");
            txtNome.setText("");
            txtCnpj.setText("");
            txtTelefone.setText("");
            txtEmail.setText("");
            txtEndereco.setText("");
            txtCidade.setText("");
            cbEstado.setSelectedIndex(0);
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Fornecedor salvo:\n"
                + "ID: " + txtId.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Dados do fornecedor alterados com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este fornecedor?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtId.setText("");
                txtNome.setText("");
                txtCnpj.setText("");
                txtTelefone.setText("");
                txtEmail.setText("");
                txtEndereco.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Fornecedor excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela(); // Volta para a tela Home
            dispose();
        });

        panel.add(btnNovo);      panel.add(btnSalvar);
        panel.add(btnAlterar);   panel.add(btnExcluir);
        panel.add(btnRelatorio); panel.add(btnRetornar);

        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}
Código: Cadastro de Fornecedores (CadastroFornecedores.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroFornecedores extends JFrame {

    public CadastroFornecedores() {
        setTitle("Cadastro de Fornecedores");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(10, 2, 5, 5));

        JTextField txtId = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtCnpj = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextField txtEmail = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtCidade = new JTextField();
        JComboBox<String> cbEstado = new JComboBox<>(new String[]{"SP", "RJ", "MG", "RS"});
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("ID:")); panel.add(txtId);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("CNPJ:")); panel.add(txtCnpj);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Email:")); panel.add(txtEmail);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtId.setText("");
            txtNome.setText("");
            txtCnpj.setText("");
            txtTelefone.setText("");
            txtEmail.setText("");
            txtEndereco.setText("");
            txtCidade.setText("");
            cbEstado.setSelectedIndex(0);
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Fornecedor salvo:\n"
                + "ID: " + txtId.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Dados do fornecedor alterados com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este fornecedor?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtId.setText("");
                txtNome.setText("");
                txtCnpj.setText("");
                txtTelefone.setText("");
                txtEmail.setText("");
                txtEndereco.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Fornecedor excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela(); // Volta para a tela Home
            dispose();
        });

        panel.add(btnNovo);      panel.add(btnSalvar);
        panel.add(btnAlterar);   panel.add(btnExcluir);
        panel.add(btnRelatorio); panel.add(btnRetornar);

        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}
Código: Cadastro de Fornecedores (CadastroFornecedores.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroFornecedores extends JFrame {

    public CadastroFornecedores() {
        setTitle("Cadastro de Fornecedores");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(10, 2, 5, 5));

        JTextField txtId = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtCnpj = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextField txtEmail = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtCidade = new JTextField();
        JComboBox<String> cbEstado = new JComboBox<>(new String[]{"SP", "RJ", "MG", "RS"});
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("ID:")); panel.add(txtId);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("CNPJ:")); panel.add(txtCnpj);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Email:")); panel.add(txtEmail);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtId.setText("");
            txtNome.setText("");
            txtCnpj.setText("");
            txtTelefone.setText("");
            txtEmail.setText("");
            txtEndereco.setText("");
            txtCidade.setText("");
            cbEstado.setSelectedIndex(0);
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Fornecedor salvo:\n"
                + "ID: " + txtId.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Dados do fornecedor alterados com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este fornecedor?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtId.setText("");
                txtNome.setText("");
                txtCnpj.setText("");
                txtTelefone.setText("");
                txtEmail.setText("");
                txtEndereco.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Fornecedor excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela(); // Volta para a tela Home
            dispose();
        });

        panel.add(btnNovo);      panel.add(btnSalvar);
        panel.add(btnAlterar);   panel.add(btnExcluir);
        panel.add(btnRelatorio); panel.add(btnRetornar);

        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}
Código: Cadastro de Fornecedores (CadastroFornecedores.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroFornecedores extends JFrame {

    public CadastroFornecedores() {
        setTitle("Cadastro de Fornecedores");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(10, 2, 5, 5));

        JTextField txtId = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtCnpj = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextField txtEmail = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtCidade = new JTextField();
        JComboBox<String> cbEstado = new JComboBox<>(new String[]{"SP", "RJ", "MG", "RS"});
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("ID:")); panel.add(txtId);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("CNPJ:")); panel.add(txtCnpj);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Email:")); panel.add(txtEmail);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtId.setText("");
            txtNome.setText("");
            txtCnpj.setText("");
            txtTelefone.setText("");
            txtEmail.setText("");
            txtEndereco.setText("");
            txtCidade.setText("");
            cbEstado.setSelectedIndex(0);
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Fornecedor salvo:\n"
                + "ID: " + txtId.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Dados do fornecedor alterados com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este fornecedor?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtId.setText("");
                txtNome.setText("");
                txtCnpj.setText("");
                txtTelefone.setText("");
                txtEmail.setText("");
                txtEndereco.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Fornecedor excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela(); // Volta para a tela Home
            dispose();
        });

        panel.add(btnNovo);      panel.add(btnSalvar);
        panel.add(btnAlterar);   panel.add(btnExcluir);
        panel.add(btnRelatorio); panel.add(btnRetornar);

        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}
        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}

------------------------------------------------------------------------------------------------------------------------------------
Código: Cadastro de Fornecedores (CadastroFornecedores.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroFornecedores extends JFrame {

    public CadastroFornecedores() {
        setTitle("Cadastro de Fornecedores");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(10, 2, 5, 5));

        JTextField txtId = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtCnpj = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextField txtEmail = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtCidade = new JTextField();
        JComboBox<String> cbEstado = new JComboBox<>(new String[]{"SP", "RJ", "MG", "RS"});
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("ID:")); panel.add(txtId);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("CNPJ:")); panel.add(txtCnpj);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Email:")); panel.add(txtEmail);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtId.setText("");
            txtNome.setText("");
            txtCnpj.setText("");
            txtTelefone.setText("");
            txtEmail.setText("");
            txtEndereco.setText("");
            txtCidade.setText("");
            cbEstado.setSelectedIndex(0);
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Fornecedor salvo:\n"
                + "ID: " + txtId.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Dados do fornecedor alterados com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este fornecedor?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtId.setText("");
                txtNome.setText("");
                txtCnpj.setText("");
                txtTelefone.setText("");
                txtEmail.setText("");
                txtEndereco.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Fornecedor excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CNPJ: " + txtCnpj.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela(); // Volta para a tela Home
            dispose();
        });

        panel.add(btnNovo);      panel.add(btnSalvar);
        panel.add(btnAlterar);   panel.add(btnExcluir);
        panel.add(btnRelatorio); panel.add(btnRetornar);

        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}
-----------------------------------------------------------------------------------------------------------------

Código: Cadastro de Recebidores (CadastroRecebidores.java)
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CadastroRecebidores extends JFrame {

    public CadastroRecebidores() {
        setTitle("Cadastro de Recebidores");
        setSize(500, 500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        JPanel panel = new JPanel(new GridLayout(10, 2, 5, 5));

        JTextField txtId = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtCpf = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextField txtEmail = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtCidade = new JTextField();
        JComboBox<String> cbEstado = new JComboBox<>(new String[]{"SP", "RJ", "MG", "RS"});
        JTextArea txtObservacoes = new JTextArea();

        panel.add(new JLabel("ID:")); panel.add(txtId);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("CPF:")); panel.add(txtCpf);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Email:")); panel.add(txtEmail);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        JButton btnNovo = new JButton("Novo");
        JButton btnSalvar = new JButton("Salvar");
        JButton btnAlterar = new JButton("Alterar");
        JButton btnExcluir = new JButton("Excluir");
        JButton btnRelatorio = new JButton("Relatório");
        JButton btnRetornar = new JButton("Retornar");

        btnNovo.addActionListener(e -> {
            txtId.setText("");
            txtNome.setText("");
            txtCpf.setText("");
            txtTelefone.setText("");
            txtEmail.setText("");
            txtEndereco.setText("");
            txtCidade.setText("");
            cbEstado.setSelectedIndex(0);
            txtObservacoes.setText("");
        });

        btnSalvar.addActionListener(e -> {
            String dados = "Recebidor salvo:\n"
                + "ID: " + txtId.getText() + "\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CPF: " + txtCpf.getText();
            JOptionPane.showMessageDialog(this, dados);
        });

        btnAlterar.addActionListener(e -> {
            JOptionPane.showMessageDialog(this, "Dados do recebidor alterados com sucesso!");
        });

        btnExcluir.addActionListener(e -> {
            int opcao = JOptionPane.showConfirmDialog(this, "Deseja excluir este recebidor?", "Confirmar", JOptionPane.YES_NO_OPTION);
            if (opcao == JOptionPane.YES_OPTION) {
                txtId.setText("");
                txtNome.setText("");
                txtCpf.setText("");
                txtTelefone.setText("");
                txtEmail.setText("");
                txtEndereco.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtObservacoes.setText("");
                JOptionPane.showMessageDialog(this, "Recebidor excluído.");
            }
        });

        btnRelatorio.addActionListener(e -> {
            String relatorio = "Relatório:\n"
                + "Nome: " + txtNome.getText() + "\n"
                + "CPF: " + txtCpf.getText();
            JOptionPane.showMessageDialog(this, relatorio);
        });

        btnRetornar.addActionListener(e -> {
            new HomeTela(); // Voltar à tela Home
            dispose();
        });

        panel.add(btnNovo);      panel.add(btnSalvar);
        panel.add(btnAlterar);   panel.add(btnExcluir);
        panel.add(btnRelatorio); panel.add(btnRetornar);

        add(panel);
        setLocationRelativeTo(null);
        setVisible(true);
    }
}
---------------------------------------------------------------------------------------------------------------------------------------

código Java contendo apenas a funcionalidade do botão "Novo", que limpa todos os campos do formulário:
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class CadastroClientesNovo {

    public static void main(String[] args) {
        JFrame frame = new JFrame("Cadastro de Clientes - Novo");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 400);

        JPanel panel = new JPanel(new GridLayout(10, 2));

        // Campos do formulário
        JTextField txtCodigo = new JTextField();
        JTextField txtNome = new JTextField();
        JTextField txtEndereco = new JTextField();
        JTextField txtBairro = new JTextField();
        JTextField txtCidade = new JTextField();
        String[] estados = {"SP", "RJ", "MG", "RS"};
        JComboBox<String> cbEstado = new JComboBox<>(estados);
        JTextField txtCep = new JTextField();
        JTextField txtTelefone = new JTextField();
        JTextArea txtObservacoes = new JTextArea();

        // Adicionando os campos ao painel com seus rótulos
        panel.add(new JLabel("Código:")); panel.add(txtCodigo);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Bairro:")); panel.add(txtBairro);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("CEP:")); panel.add(txtCep);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        // Botão Novo
        JButton btnNovo = new JButton("Novo");
        btnNovo.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                txtCodigo.setText("");
                txtNome.setText("");
                txtEndereco.setText("");
                txtBairro.setText("");
                txtCidade.setText("");
                cbEstado.setSelectedIndex(0);
                txtCep.setText("");
                txtTelefone.setText("");
                txtObservacoes.setText("");
            }
        });

        // Adiciona o botão ao painel
        panel.add(btnNovo);

        frame.add(panel);
        frame.setVisible(true);
    }
}

código Java contendo apenas a funcionalidade do botão "Alterar", que simula a alteração de dados preenchidos, exibindo uma mensagem com os valores atuais dos campos:
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class CadastroClientesAlterar {

    public static void main(String[] args) {
        JFrame frame = new JFrame("Cadastro de Clientes - Alterar");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 400);

        JPanel panel = new JPanel(new GridLayout(10, 2));

        // Campos do formulário
        JTextField txtCodigo = new JTextField("123");
        JTextField txtNome = new JTextField("João da Silva");
        JTextField txtEndereco = new JTextField("Rua Exemplo, 123");
        JTextField txtBairro = new JTextField("Centro");
        JTextField txtCidade = new JTextField("São Paulo");
        String[] estados = {"SP", "RJ", "MG", "RS"};
        JComboBox<String> cbEstado = new JComboBox<>(estados);
        cbEstado.setSelectedItem("SP");
        JTextField txtCep = new JTextField("01000-000");
        JTextField txtTelefone = new JTextField("(11) 99999-9999");
        JTextArea txtObservacoes = new JTextArea("Cliente antigo");

        // Adicionando os campos ao painel com seus rótulos
        panel.add(new JLabel("Código:")); panel.add(txtCodigo);
        panel.add(new JLabel("Nome:")); panel.add(txtNome);
        panel.add(new JLabel("Endereço:")); panel.add(txtEndereco);
        panel.add(new JLabel("Bairro:")); panel.add(txtBairro);
        panel.add(new JLabel("Cidade:")); panel.add(txtCidade);
        panel.add(new JLabel("Estado:")); panel.add(cbEstado);
        panel.add(new JLabel("CEP:")); panel.add(txtCep);
        panel.add(new JLabel("Telefone:")); panel.add(txtTelefone);
        panel.add(new JLabel("Observações:")); panel.add(txtObservacoes);

        // Botão Alterar
        JButton btnAlterar = new JButton("Alterar");
        btnAlterar.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                // Simula uma alteração e exibe os dados atuais
                String dados = "Dados alterados:\n" +
                        "Código: " + txtCodigo.getText() + "\n" +
                        "Nome: " + txtNome.getText() + "\n" +
                        "Endereço: " + txtEndereco.getText() + "\n" +
                        "Bairro: " + txtBairro.getText() + "\n" +
                        "Cidade: " + txtCidade.getText() + "\n" +
                        "Estado: " + cbEstado.getSelectedItem() + "\n" +
                        "CEP: " + txtCep.getText() + "\n" +
                        "Telefone: " + txtTelefone.getText() + "\n" +
                        "Observações: " + txtObservacoes.getText();
                JOptionPane.showMessageDialog(frame, dados, "Alteração Realizada", JOptionPane.INFORMATION_MESSAGE);
            }
        });
-----------------------------------------------------------------------------------------------------------------------------------------

