# TugasPBO14
package MahasiswaApp;
import java.sql.*;
import javax.swing.table.*;
import java.text.SimpleDateFormat;
import java.util.Date;

import javax.swing.JOptionPane;
import java.sql.Connection;
import java.sql.SQLException;

import java.util.logging.Level;
import java.util.logging.Logger;

import net.sf.jasperreports.engine.JRException;
import net.sf.jasperreports.engine.JasperCompileManager;
import net.sf.jasperreports.engine.JasperFillManager;
import net.sf.jasperreports.engine.JasperPrint;
import net.sf.jasperreports.engine.JasperReport;
import net.sf.jasperreports.engine.design.JRDesignQuery;
import net.sf.jasperreports.engine.design.JasperDesign;
import net.sf.jasperreports.engine.xml.JRXmlLoader;
import net.sf.jasperreports.view.JasperViewer;

/**
 *
 * @author User
 */
public class FormMahasiswa extends javax.swing.JFrame {
     public String TANGGAL_LAHIR;

    /**
     * Creates new form FormMahasiswa
     */
    public FormMahasiswa() {
        initComponents();
        tampil_data();
    }
    Connection conn;
    PreparedStatement pst;
    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        jScrollPane1 = new javax.swing.JScrollPane();
        jTable1 = new javax.swing.JTable();
        jDayChooser1 = new com.toedter.calendar.JDayChooser();
        jLabel1 = new javax.swing.JLabel();
        NIM = new javax.swing.JLabel();
        NAMA = new javax.swing.JLabel();
        TANGGALLAHIR = new javax.swing.JLabel();
        JURUSAN = new javax.swing.JLabel();
        ALAMAT = new javax.swing.JLabel();
        nim = new javax.swing.JTextField();
        nama = new javax.swing.JTextField();
        jurusan = new javax.swing.JTextField();
        alamat = new javax.swing.JTextField();
        bt_TAMBAH = new javax.swing.JButton();
        bt_UBAH = new javax.swing.JButton();
        bt_HAPUS = new javax.swing.JButton();
        bt_CETAK = new javax.swing.JButton();
        jScrollPane2 = new javax.swing.JScrollPane();
        TabelMahasiswa = new javax.swing.JTable();
        TANGGAL = new javax.swing.JFormattedTextField();

        jTable1.setModel(new javax.swing.table.DefaultTableModel(
            new Object [][] {
                {null, null, null, null},
                {null, null, null, null},
                {null, null, null, null},
                {null, null, null, null}
            },
            new String [] {
                "Title 1", "Title 2", "Title 3", "Title 4"
            }
        ));
        jScrollPane1.setViewportView(jTable1);

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

        jLabel1.setFont(new java.awt.Font("Tahoma", 1, 18)); // NOI18N
        jLabel1.setText("DATA MAHASISWA");

        NIM.setFont(new java.awt.Font("Tahoma", 0, 12)); // NOI18N
        NIM.setText("NIM");

        NAMA.setText("NAMA");

        TANGGALLAHIR.setText("TANGGAL LAHIR");

        JURUSAN.setText("JURUSAN");

        ALAMAT.setText("ALAMAT");

        nim.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                nimActionPerformed(evt);
            }
        });

        bt_TAMBAH.setText("TAMBAH");
        bt_TAMBAH.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                bt_TAMBAHActionPerformed(evt);
            }
        });

        bt_UBAH.setText("UBAH");
        bt_UBAH.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                bt_UBAHActionPerformed(evt);
            }
        });

        bt_HAPUS.setText("HAPUS");
        bt_HAPUS.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                bt_HAPUSActionPerformed(evt);
            }
        });

        bt_CETAK.setText("CETAK");
        bt_CETAK.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                bt_CETAKActionPerformed(evt);
            }
        });

        TabelMahasiswa.setModel(new javax.swing.table.DefaultTableModel(
            new Object [][] {
                {null, null, null, null},
                {null, null, null, null},
                {null, null, null, null},
                {null, null, null, null}
            },
            new String [] {
                "NIM", "NAMA", "TANGGAL LAHIR", "ALAMAT"
            }
        ));
        TabelMahasiswa.addAncestorListener(new javax.swing.event.AncestorListener() {
            public void ancestorMoved(javax.swing.event.AncestorEvent evt) {
            }
            public void ancestorAdded(javax.swing.event.AncestorEvent evt) {
                TabelMahasiswaAncestorAdded(evt);
            }
            public void ancestorRemoved(javax.swing.event.AncestorEvent evt) {
            }
        });
        jScrollPane2.setViewportView(TabelMahasiswa);

        TANGGAL.setFormatterFactory(new javax.swing.text.DefaultFormatterFactory(new javax.swing.text.DateFormatter()));

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(124, 124, 124)
                        .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 178, javax.swing.GroupLayout.PREFERRED_SIZE))
                    .addGroup(layout.createSequentialGroup()
                        .addContainerGap()
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                            .addGroup(layout.createSequentialGroup()
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING, false)
                                        .addComponent(NAMA, javax.swing.GroupLayout.Alignment.LEADING, javax.swing.GroupLayout.DEFAULT_SIZE, 43, Short.MAX_VALUE)
                                        .addComponent(NIM, javax.swing.GroupLayout.Alignment.LEADING, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
                                    .addComponent(TANGGALLAHIR, javax.swing.GroupLayout.PREFERRED_SIZE, 93, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addGap(81, 81, 81)
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(nim)
                                    .addComponent(nama, javax.swing.GroupLayout.DEFAULT_SIZE, 196, Short.MAX_VALUE)
                                    .addComponent(TANGGAL)))
                            .addGroup(layout.createSequentialGroup()
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(JURUSAN, javax.swing.GroupLayout.PREFERRED_SIZE, 61, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(ALAMAT, javax.swing.GroupLayout.PREFERRED_SIZE, 43, javax.swing.GroupLayout.PREFERRED_SIZE))
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 113, Short.MAX_VALUE)
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(jurusan, javax.swing.GroupLayout.PREFERRED_SIZE, 196, javax.swing.GroupLayout.PREFERRED_SIZE)
                                    .addComponent(alamat, javax.swing.GroupLayout.Alignment.TRAILING, javax.swing.GroupLayout.PREFERRED_SIZE, 196, javax.swing.GroupLayout.PREFERRED_SIZE)))))
                    .addGroup(layout.createSequentialGroup()
                        .addGap(29, 29, 29)
                        .addComponent(bt_TAMBAH, javax.swing.GroupLayout.PREFERRED_SIZE, 81, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addGap(18, 18, 18)
                        .addComponent(bt_UBAH)
                        .addGap(18, 18, 18)
                        .addComponent(bt_HAPUS)
                        .addGap(18, 18, 18)
                        .addComponent(bt_CETAK))
                    .addGroup(layout.createSequentialGroup()
                        .addGap(19, 19, 19)
                        .addComponent(jScrollPane2, javax.swing.GroupLayout.PREFERRED_SIZE, 421, javax.swing.GroupLayout.PREFERRED_SIZE)))
                .addContainerGap(35, Short.MAX_VALUE))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 37, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(NIM, javax.swing.GroupLayout.PREFERRED_SIZE, 21, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(nim, javax.swing.GroupLayout.PREFERRED_SIZE, 21, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(NAMA, javax.swing.GroupLayout.PREFERRED_SIZE, 24, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(nama, javax.swing.GroupLayout.PREFERRED_SIZE, 21, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(34, 34, 34)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(TANGGALLAHIR, javax.swing.GroupLayout.PREFERRED_SIZE, 24, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(TANGGAL, javax.swing.GroupLayout.PREFERRED_SIZE, 24, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(24, 24, 24)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(JURUSAN, javax.swing.GroupLayout.PREFERRED_SIZE, 24, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(jurusan, javax.swing.GroupLayout.PREFERRED_SIZE, 21, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(18, 18, 18)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(alamat, javax.swing.GroupLayout.PREFERRED_SIZE, 48, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(ALAMAT, javax.swing.GroupLayout.PREFERRED_SIZE, 24, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(30, 30, 30)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(bt_TAMBAH)
                    .addComponent(bt_UBAH)
                    .addComponent(bt_CETAK)
                    .addComponent(bt_HAPUS))
                .addGap(39, 39, 39)
                .addComponent(jScrollPane2, javax.swing.GroupLayout.PREFERRED_SIZE, 110, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addContainerGap(25, Short.MAX_VALUE))
        );

        pack();
    }// </editor-fold>                        

    private void bt_TAMBAHActionPerformed(java.awt.event.ActionEvent evt) {                                          
        // TODO add your handling code here:
       String tampilan ="yyyy-MM-dd" ; 
        SimpleDateFormat fm = new SimpleDateFormat(tampilan); 
        String TANGGAL_LAHIR;
         TANGGAL_LAHIR = String.valueOf(fm.format(TANGGAL.getText()));
         try{
        String sql="insert into mahasiswa values('"
        +NIM.getText()+"','"
        +NAMA.getText()+"','"
        +TANGGAL_LAHIR+"','"
        +JURUSAN.getText()+"','"
        +ALAMAT.getText()+"')";
        java.sql.Connection conn=(java.sql.Connection)MahasiswaApp.Koneksi.getKoneksi();
        java.sql.PreparedStatement pst=conn.prepareStatement(sql);
        pst.execute();
        JOptionPane.showMessageDialog(null, "Berhasil disimpan");
        
        }
        catch (Exception e){
            JOptionPane.showMessageDialog(null, "Gagal disimpan");
            System.out.println(e.getMessage());
            tampil_data();
        }                   
                           
    }                                         

    private void bt_HAPUSActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
        try{
            java.sql.Connection conn=(java.sql.Connection)MahasiswaApp.Koneksi.getKoneksi();
            String sql = "delete from mahasiswa where NIM='"+NIM.getText()+"' ";
            java.sql.PreparedStatement pst = conn.prepareStatement(sql);
            pst.executeUpdate();
            
            JOptionPane.showMessageDialog(null,"Data berhasil di hapus");
            tampil_data();
        }
        catch (Exception e){
            JOptionPane.showMessageDialog(null,"Proses Penghapusan Gagal");
            System.out.println(e.getMessage());
      }
    }                                        

    private void bt_UBAHActionPerformed(java.awt.event.ActionEvent evt) {                                        
        // TODO add your handling code here:
        try{
            java.sql.Connection conn=(java.sql.Connection)MahasiswaApp.Koneksi.getKoneksi();
            String sql="update mahasiswa set NAMA='" + NAMA.getText()+"', "
            + "TANGGAL_LAHIR='"+TANGGAL_LAHIR+
            "', JURUSAN='"+JURUSAN.getText()+
            "', ALAMAT='"+ALAMAT.getText()+
            "' where NIM='"+NIM.getText()+"'";
    java.sql.PreparedStatement pst = conn.prepareStatement(sql);
    pst.executeUpdate();
    JOptionPane.showMessageDialog(null,"Data berhasil di Ubah");
    tampil_data();
    }
        catch (Exception e){
        JOptionPane.showMessageDialog(null,"Proses Edit data Gagal");
        System.out.println(e.getMessage());
        }             
    }                                       

    private void TabelMahasiswaAncestorAdded(javax.swing.event.AncestorEvent evt) {                                             
        // TODO add your handling code here:
         int baris= TabelMahasiswa.getSelectedRow();
        NIM.setText(TabelMahasiswa.getValueAt(baris, 0).toString());
        NAMA.setText(TabelMahasiswa.getValueAt(baris, 1).toString());
        JURUSAN.setText(TabelMahasiswa.getValueAt(baris, 3).toString());
        ALAMAT.setText(TabelMahasiswa.getValueAt(baris, 4).toString());
        
        try {
            int TANGGAL_LAHIR = TabelMahasiswa.getSelectedRow();
            Date date = new SimpleDateFormat("yyyy-MM-dd").parse((String)TabelMahasiswa.getValueAt(TANGGAL_LAHIR, 2));
            TANGGAL.getText();       
        }
        catch (Exception e){
        JOptionPane.showMessageDialog(null,"Ada Kesalahan");
        System.out.println(e.getMessage());
        }
    }                                            

    private void bt_CETAKActionPerformed(java.awt.event.ActionEvent evt) {  
         try {
             // TODO add your handling code here:
             Class.forName("com.mysql.jdbc.Driver");
         } catch (ClassNotFoundException ex) {
             Logger.getLogger(FormMahasiswa.class.getName()).log(Level.SEVERE, null, ex);
         }
         try {
             conn = DriverManager.getConnection("jdbc:mysql://localhost/db_mahasiswa","root","");
         } catch (SQLException ex) {
             Logger.getLogger(FormMahasiswa.class.getName()).log(Level.SEVERE, null, ex);
         }
            JasperDesign jdesign = JRXmlLoader.load("C:\\User\\Documents\\NetBeansProjects\\mahasiswa\\src\\dbsmahasiswa\\report_mahasiswa.jrxml");
            String query = "select * from mahasiswa";
            
            JRDesignQuery updateQuery = new JRDesignQuery();
            updateQuery.setText(query);
            
            jdesign.setQuery(updateQuery);
            
            JasperReport jreport = JasperCompileManager.compileReport(jdesign);
            JasperPrint jprint = JasperFillManager.fillReport(jreport, null,conn);
            
            JasperViewer.viewReport(jprint);
    
            
        } catch (ClassNotFoundException ex) {
            Logger.getLogger(FormMahasiswa.class.getName()).log(Level.SEVERE, null, ex);
        } catch (SQLException ex) {
            Logger.getLogger(FormMahasiswa.class.getName()).log(Level.SEVERE, null, ex);
        } catch (JRException ex) {
            Logger.getLogger(FormMahasiswa.class.getName()).log(Level.SEVERE, null, ex);
        
    }                                                                      
         
    }                                        

    private void nimActionPerformed(java.awt.event.ActionEvent evt) {                                    
        // TODO add your handling code here:
    }                                   
    public void tampil_data(){
        DefaultTableModel TABEL =new DefaultTableModel();
        TABEL.addColumn("NIM");
        TABEL.addColumn("NAMA");
        TABEL.addColumn("TGL LAHIR");
        TABEL.addColumn("JURUSAN");
        TABEL.addColumn("ALAMAT");
    try {
        java.sql.Connection conn=(java.sql.Connection)MahasiswaApp.Koneksi.getKoneksi();
        String sql="select*From Mahasiswa";
        java.sql.PreparedStatement pst =conn.prepareStatement(sql);
        ResultSet rs=pst.executeQuery(sql);
        while (rs.next())
        {
        TABEL.addRow(new Object[]{
            rs.getString(1),
            rs.getString(2),
            rs.getString(3),
            rs.getString(4),
            rs.getString(5)});
        }
        TabelMahasiswa.setModel(TABEL);
        }
    catch (Exception e){
    } 
     
    /**
     * @param args the command line arguments
     */
    public static void main (String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ClassNotFoundException ex) {
            java.util.logging.Logger.getLogger(FormMahasiswa.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (InstantiationException ex) {
            java.util.logging.Logger.getLogger(FormMahasiswa.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (IllegalAccessException ex) {
            java.util.logging.Logger.getLogger(FormMahasiswa.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (javax.swing.UnsupportedLookAndFeelException ex) {
            java.util.logging.Logger.getLogger(FormMahasiswa.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new FormMahasiswa().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify                     
    private javax.swing.JLabel ALAMAT;
    private javax.swing.JLabel JURUSAN;
    private javax.swing.JLabel NAMA;
    private javax.swing.JLabel NIM;
    private javax.swing.JFormattedTextField TANGGAL;
    private javax.swing.JLabel TANGGALLAHIR;
    private javax.swing.JTable TabelMahasiswa;
    private javax.swing.JTextField alamat;
    private javax.swing.JButton bt_CETAK;
    private javax.swing.JButton bt_HAPUS;
    private javax.swing.JButton bt_TAMBAH;
    private javax.swing.JButton bt_UBAH;
    private com.toedter.calendar.JDayChooser jDayChooser1;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JScrollPane jScrollPane1;
    private javax.swing.JScrollPane jScrollPane2;
    private javax.swing.JTable jTable1;
    private javax.swing.JTextField jurusan;
    private javax.swing.JTextField nama;
    private javax.swing.JTextField nim;
    // End of variables declaration                   
}
