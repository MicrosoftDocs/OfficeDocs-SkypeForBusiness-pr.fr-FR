---
title: 'Lync Server 2013 : créer ou modifier une configuration de partenaire XMPP'
TOCTitle: Créer ou modifier une configuration de partenaire XMPP
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ552447(v=OCS.15)
ms:contentKeyID: 49296846
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier une configuration de partenaire XMPP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync Server 2013 intègre un proxy XMPP (Extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool de serveurs frontaux. Pour autoriser les connexions d’autres déploiements XMPP, vous devez configurer XMPP dans le Panneau de configuration Lync Server. Vous configurez les paramètres par domaine XMPP. Pour créer une nouvelle association partenaire, procédez comme suit :

## Pour créer un nouveau partenaire fédéré ou modifier une configuration existante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Partenaires fédérés XMPP**.

4.  Pour créer une configuration, cliquez sur **Nouveau**.

5.  Pour modifier une configuration existante, sélectionnez-la et cliquez sur **Modifier**

6.  Pour créer ou modifier des configurations de **Partenaires fédérés XMPP**, définissez les paramètres suivants :

7.  **Domaine principal** (obligatoire). Le domaine principal correspond au domaine de base du partenaire XMPP. Par exemple, vous pouvez entrer **fabrikam.com** comme nom de domaine du partenaire XMPP. Cette entrée est obligatoire.

8.  **Description**. La description correspond aux remarques ou autres informations d’identification de la configuration spécifique. Cette entrée est facultative.

9.  **Autres domaines**. Autres domaines faisant partie du domaine de votre partenaire XMPP et qui doivent être intégrés aux communications XMPP autorisées. Par exemple, si le domaine principal est **fabrikam.com**, vous devez répertorier tous les autres domaines situés sous fabrikam.com avec lesquels vous êtes appelé à communiquer via XMPP. Vous pouvez ensuite entrer **corp.fabrikam.com** et **it.fabrikam.com**, par exemple, en tant que domaine XMPP d’entreprise et domaine XMPP des technologies de l’information sous le domaine XMPP principal de fabrikam.com.

10. **Type de partenaire**. Le paramètre **Type de partenaire** est obligatoire et propose trois options dans un menu déroulant. Vous devez sélectionner l’une des options suivantes pour décrire et appliquer les contacts à ajouter. Vous avez le choix entre :
    
      - **Fédéré**. Un type de partenaire **Fédéré** est une connexion approuvée entre un déploiement partenaire Lync Server ou Office Communications Server 2007 R2.
    
      - **Public vérifié**. L’option **Public vérifié** signifie que les contacts qui sont vérifiés par le fournisseur dans le cadre d’un déploiement peuvent être ajoutés à la liste de contacts de votre utilisateur. L’utilisateur Lync ou Lync peut envoyer des invitations ou en accepter de la part du contact partenaire.
    
      - **Public non vérifié**. Une relation **Public non vérifié** implique que le statut entre deux déploiements n’est ni établi ni vérifiable. Un utilisateur Lync doit inviter le contact non vérifié pour que ce dernier puisse ajouter l’utilisateur Lync à sa liste de contacts. Par exemple, Google GTalk n’est pas un service XMPP public vérifié quand il est associé à Lync Server. Un utilisateur GTalk n’est donc pas en mesure d’ajouter l’utilisateur Lync comme contact sauf si l’utilisateur Lync lui envoie une invitation explicite.

11. Remarques concernant la négociation de flux, ainsi que les méthodes de sécurité TLS (Transport Layer Security) et SASL (Software Authentication and Security Layer) :
    
    La **XMPP Standards Foundation** (XSF) et la **Internet Engineering Task Force** (IETF) définissent un ensemble de règles et de normes qui régissent l’utilisation et la gestion des certificats clients TLS, des certificats de serveur TLS et du mécanisme SASL. L’utilisation de TLS et SASL constitue le processus requis pour la sécurisation du flux XMPP. D’après le document de la XMPP Standards Foundation, **XEP-0178**, « spécifie un flux de protocole recommandé dans le cadre de l’utilisation du mécanisme SASL EXTERNAL avec des certificats PKIX, en particulier quand un service XMPP indique que TLS est obligatoire pour la négociation. ». PKIX, comme mentionné dans la documentation XSF, fait référence à une infrastructure à clé publique, connue aussi sous le nom de PKI.
    
    Reportez-vous au document de la XSF, XEP-0178, pour plus d’informations sur les conditions XMPP requises. Pour plus d’informations, reportez-vous à « XEP-0178: Best Practices for Use of SASL EXTERNAL with Certificates ». <http://xmpp.org/extensions/xep-0178.html>
    
    Reportez-vous au document de l’IETF « Extensible Messaging and Presence Protocol (XMPP): Core », Section 5.0, STARTTLS Negotiation <http://tools.ietf.org/html/rfc6120>.
    
      - **Négociation TLS**. Définit les règles de négociation TLS. Un service XMPP peut nécessiter TLS, peut rendre TLS facultatif ou vous pouvez décider de ne pas prendre en charge TLS. Si vous sélectionnez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire. Pour afficher tous les paramètres possibles et les détails pour la négociation SASL, TLS et Dialback (dont les configurations incorrectes et les erreurs connues), consultez la rubrique [Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          -   
            **Obligatoire**. Le service XMPP nécessite la négociation TLS.
        
          -   
            **Facultatif**. Le service XMPP indique que TLS est obligatoire pour la négociation.
        
          -   
            **Non pris en charge**. Le service XMPP ne prend pas en charge TLS.
    
      - **Négociation SASL**. Définit les règles de négociation SASL. Un service XMPP peut nécessiter SASL, peut rendre SASL facultatif ou vous pouvez décider de ne pas prendre en charge SASL. Si vous sélectionnez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire.
        
        > [!WARNING]  
        > SASL requiert TLS. Pour utiliser SASL, TLS doit être requis ou facultatif. Toute configuration qui définit SASL comme étant requis ou facultatif doit disposer d’une prise en charge TSL. Quand vous cliquez sur <strong>Valider</strong> pour enregistrer vos modifications, si vous n’avez pas défini TLS sur requis ou facultatif, un message vous avertira que SASL doit avoir une prise en charge TLS et que vos modifications ne seront pas enregistrées. Pour résoudre l’erreur, définissez TLS sur <strong>Requis</strong> ou <strong>Facultatif</strong>. Si l’utilisation de SASL est facultative et que la prise en charge de la négociation TLS est impossible, vous devez définir la négociation SASL sur <strong>Non pris en charge</strong>. Confirmez avec le service XMPP les conditions requises en matière de flux de négociation pour TLS et SASL ou le service sera interrompu. 

          - **Obligatoire**. Le service XMPP nécessite la négociation SASL.
        
          -   
            **Facultatif**. Le service XMPP indique que SASL est obligatoire pour la négociation.
        
          -   
            **Non pris en charge**. Le service XMPP ne prend pas en charge SASL.
    
      - **Dialback Negotiation**. Dialback Negotiation est défini par la XSF dans le document **XEP-220 : Server Dialback** <http://xmpp.org/extensions/xep-0220.html>. Le processus de rappel utilise le DNS (Domain Name System) et un serveur de référence pour vérifier que la demande provient d’un partenaire XMPP valide. À cet effet, le serveur d’origine crée un message d’un type spécifique avec une clé de rappel générée et consulte le serveur de réception sur le DNS. Le serveur d’origine envoie la clé dans un flux XML dans la consultation DNS obtenue, vraisemblablement le serveur de réception. À réception de la clé sur le flux XML, le serveur de réception ne répond pas au serveur d’origine, mais envoie la clé à un serveur de référence connu. Ce dernier vérifie si la clé est valide ou non. Si elle ne l’est pas, le serveur de réception ne répond pas au serveur d’origine. Si la clé est valide, le serveur de réception informe le serveur d’origine que l’identité et la clé sont valides et que la conversation peut commencer.
        
        Il existe deux états valides pour la **négociation de rappel** :
        
          -   
            **True**. Le serveur XMPP est configuré pour utiliser Dialback Negotiation si une demande doit être reçue en provenance d’un serveur d’origine.
        
          -   
            **False**. Le serveur XMPP n’est pas configuré pour utiliser Dialback Negotiation. Si une demande doit être reçue en provenance d’un serveur d’origine, elle est ignorée.

