---
title: Vérification de l’environnement Lync Server 2010
TOCTitle: Vérification de l’environnement Lync Server 2010
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205231(v=OCS.15)
ms:contentKeyID: 49298705
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de l’environnement Lync Server 2010

 

_**Dernière rubrique modifiée :** 2012-10-19_

Avant de déployer Lync Server 2013 dans un état de coexistence avec Lync Server 2010, vous devez vérifier que les services Lync Server 2010 ont été configurés et démarrés. Il est important d’identifier les principaux services et fonctionnalités utilisés dans votre environnement hérité avant de commencer le déploiement d’un pool pilote Lync Server 2013. Préalablement au déploiement de services XMPP Microsoft Lync Server 2013 dans un état de coexistence avec un déploiement XMPP hérité, assurez-vous que les services XMPP hérités ont bien été configurés et démarrés, et déterminez quel partenaire fédéré est pris en charge par la configuration XMPP héritée. Le processus de vérification de votre déploiement Lync Server 2010 hérité comprend les étapes suivantes :

  - Vérification du démarrage des services Lync Server 2010

  - Revue de la topologie et des utilisateurs Lync Server 2010

  - Vérification des paramètres de fédération et du serveur Edge

  - Vérification des services XMPP et des partenaires fédérés

**Pour vérifier que les services Lync Server 2010 sont démarrés**

1.  Depuis le serveur frontal Lync Server 2010, accédez à Outils d’administration\\Applet Services.

2.  Vérifiez que les services suivants sont exécutés sur le serveur frontal :
    
    ![Liste des services s’exécutant sur le serveur frontal](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste des services s’exécutant sur le serveur frontal")

**Pour consulter la topologie Lync Server 2010 dans le Panneau de configuration Lync Server**

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Sélectionnez **Topologie** . Vérifiez que les différents serveurs de votre déploiement Lync Server 2010 sont affichés.
    
    ![Page de la topologie du Panneau de configuration de Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Page de la topologie du Panneau de configuration de Lync Server 2010")

**Pour consulter les utilisateurs Lync Server 2010 dans le Panneau de configuration Lync Server**

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Sélectionnez **Utilisateurs** , puis cliquez sur **Rechercher** .

3.  Vérifiez que la colonne **Pool de serveurs d’inscriptions** fait référence au pool Lync Server 2010 pour chaque utilisateur répertorié.
    
    ![Panneau de configuration Lync Server 2010 listant les utilisateurs](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panneau de configuration Lync Server 2010 listant les utilisateurs")

**Pour vérifier les paramètres de fédération et du serveur Edge Lync Server 2010**

1.  Démarrez le générateur de topologie.

2.  Sélectionnez **Télécharger une topologie à partir d’un déploiement existant**.

3.  Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier .tbxml par défaut.

4.  Développez le nœud Lync Server 2010 pour afficher tous les rôles serveur disponibles dans le déploiement.

5.  Sélectionnez le nœud du site et vérifiez si l’option **Attribution de l’itinéraire de fédération du site** est définie.
    
    ![Générateur de topologie, itinéraire de fédération de sites](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Générateur de topologie, itinéraire de fédération de sites")

6.  Sélectionnez ensuite le serveur Standard Edition ou le pool frontal Enterprise Edition. Vérifiez si un pool Edge a été configuré pour les médias sous **Associations**.
    
    ![Générateur de topologie montrant des serveurs et des pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Générateur de topologie montrant des serveurs et des pools")

7.  Enfin, sélectionnez le pool Edge et vérifiez si un pool de tronçon suivant est configuré sous **Sélection du tronçon suivant**.
    
    ![Générateur de topologie, Sélection du tronçon suivant](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Générateur de topologie, Sélection du tronçon suivant")

**Pour vérifier la configuration des services XMPP et des partenaires fédérés**

1.  À partir du serveur XMPP hérité, naviguez vers l’applet Outils/Services d’administration.

2.  Vérifiez que le service de passerelle XMPP Office Communications Server est démarré.
    
    ![Service de la passerelle XMPP d’Office Communications Server](images/JJ205231.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de la passerelle XMPP d’Office Communications Server")

