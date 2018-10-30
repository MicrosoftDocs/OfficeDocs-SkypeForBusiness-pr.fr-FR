---
title: Déploiement du serveur Edge pilote
TOCTitle: Déploiement du serveur Edge pilote
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205306(v=OCS.15)
ms:contentKeyID: 49299056
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement du serveur Edge pilote

 

_**Dernière rubrique modifiée :** 2012-10-19_

Cette rubrique met en avant les paramètres de configuration dont vous devez avoir connaissance avant de déployer votre serveur EdgeLync Server 2013. Les processus de déploiement et de configuration de Lync Server 2013 sont très similaires à Lync Server 2010. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour des étapes détaillées, reportez-vous à [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation relative au déploiement ; celle-ci décrit le processus de déploiement et donne des informations de configuration pour l’accès des utilisateurs externes.

À mesure que vous parcourez l’Assistant **Définir un nouveau pool Edge** , examinez les principaux paramètres de configuration mentionnés aux étapes suivantes. Notez que seules quelques pages de l’Assistant **Définir un nouveau pool Edge** sont illustrées.

**Pour définir un pool Edge**

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Accédez au nœud Lync Server 2013. Cliquez avec le bouton droit sur **Pools Edge** , puis cliquez sur **Nouveau pool de serveurs Edge** .
    
    ![Boîte de dialogue Définir le nouveau pool Edge](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue Définir le nouveau pool Edge")

3.  Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur** .
    
    ![Boîte de dialogue Définir le nom de domaine complet du pool Edge](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Boîte de dialogue Définir le nom de domaine complet du pool Edge")

4.  Dans la page **Sélectionner les fonctionnalités** , n’activez pas la fédération ni la fédération XMPP. La fédération et la fédération XMPP sont toutes deux actuellement acheminées via le serveur EdgeLync Server 2010 hérité. Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")

5.  Ensuite, continuez à remplir les pages suivantes de l’Assistant : **Noms de domaine complets externes** , **Définir l’adresse IP interne** et **Définir l’adresse IP externe** .

6.  Dans la page **Définir le tronçon suivant**, sélectionnez le directeur pour le tronçon suivant du Lync Server 2010 pool de serveurs Edge.
    
    ![Boîte de dialogue Définir le tronçon suivant](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Boîte de dialogue Définir le tronçon suivant")

7.  Dans la page **Pools frontaux ou de médiation associés** , n’associez pas de pool à ce pool de serveurs Edge à ce stade. Le trafic multimédia externe est actuellement acheminé via le serveur EdgeLync Server 2010 hérité. Ce paramètre sera configuré lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue Pools frontaux associés](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Boîte de dialogue Pools frontaux associés")

8.  Cliquez sur **Terminer** , puis sur **Publier** pour publier la topologie.

9.  Suivez les étapes décrites dans [Installation des serveurs Edge pour Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services.

Il est essentiel de bien respecter les consignes fournies dans la rubrique [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) de la documentation de déploiement. Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur.

Vous devriez maintenant avoir un serveur Edge Lync Server 2010 hérité déployé en parallèle avec un déploiement de serveur Edge Lync Server 2013. Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante.

