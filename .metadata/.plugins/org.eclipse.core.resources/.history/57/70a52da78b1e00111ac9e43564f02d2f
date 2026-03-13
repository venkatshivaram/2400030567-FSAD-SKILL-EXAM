package com.klef.fsad.exam;

import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.Transaction;
import org.hibernate.cfg.Configuration;
import org.hibernate.query.Query;

public class ClientDemo {

    public static void main(String[] args) {
        Configuration configuration = new Configuration();
        configuration.configure("hibernate.cfg.xml");
        SessionFactory sessionFactory = configuration.buildSessionFactory();
        Session session = sessionFactory.openSession();
        Transaction transaction = session.beginTransaction();

        Delivery delivery = new Delivery();
        delivery.setId(1);
        delivery.setName("Laptop");
        delivery.setDate("2026-03-13");
        delivery.setStatus("Pending");
        delivery.setDestination("Vijayawada");

        session.save(delivery);
        System.out.println("Record inserted successfully.");

        transaction.commit();

        transaction = session.beginTransaction();

        String hql = "DELETE FROM Delivery WHERE id = ?1";
        Query<?> query = session.createQuery(hql);
        query.setParameter(1, 1);
        int result = query.executeUpdate();

        System.out.println("Records deleted: " + result);

        transaction.commit();
        session.close();
        sessionFactory.close();
    }
}
