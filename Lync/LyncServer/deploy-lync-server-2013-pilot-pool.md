---
title: Déploiement du pool pilote Lync Server 2013
TOCTitle: Déploiement du pool pilote Lync Server 2013
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205144(v=OCS.15)
ms:contentKeyID: 49298472
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement du pool pilote Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-22_

L’une des premières étapes requises pour la migration Lync Server 2013 consiste à déployer un pool pilote. Un pool pilote correspond à l’endroit auquel vous testez la coexistence de Lync Server 2013 avec votre déploiement de Lync Server 2010. La coexistence est un état temporaire qui dure jusqu’à ce que vous déplaciez l’ensemble des utilisateurs et des pools vers Lync Server 2013.

Lorsque vous déployez un pool pilote, vous utilisez l’Assistant Définir un nouveau pool frontal. Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool pilote Lync Server 2013 que dans votre pool Lync Server 2010. Si vous avez déployé un serveur d’archivage, un serveur de surveillance ou System Center Operations Manager pour l’archivage ou la surveillance de votre environnement Lync Server 2010 et que vous souhaitez continuer l’archivage ou la surveillance durant la migration, vous devez également déployer ces fonctionnalités dans votre environnement pilote. La version que vous avez déployée pour archiver et surveiller votre environnement Lync Server 2010 ne capture pas de données dans votre environnement Lync Server 2013.

> [!NOTE]  
> La procédure qui suit traite des fonctionnalités et paramètres à considérer dans le cadre du processus de déploiement général de votre pool pilote. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour en connaître les étapes précises, reportez-vous au guide de déploiement intitulé <a href="lync-server-2013-deploying-lync-server.md">Déploiement de Lync Server 2013</a>.

**Pour déployer un pool pilote Lync Server 2013**

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Développez l’arborescence jusqu’à atteindre **Lync Server 2013Pools frontaux Enterprise Edition** .

3.  Cliquez avec le bouton droit sur **Pools frontaux Enterprise Edition** et sélectionnez **Nouveau pool frontal** .
    
    ![Sous-menu de sélection du pool de serveurs du Générateur de topologie](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Sous-menu de sélection du pool de serveurs du Générateur de topologie")

4.  Entrez le nom de domaine complet du pool. Lorsque vous définissez votre pool pilote, vous pouvez choisir de déployer un pool de serveurs frontaux Enterprise Edition ou un serveur Standard Edition. Lync Server 2013 n’exige pas que les fonctionnalités de votre pool pilote correspondent à celles déployées dans votre pool hérité.
    
    > [!WARNING]  
    > Le nom de domaine complet du pool ou serveur que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool Lync Server 2010 actuellement déployé ni à tout autre serveur actuellement déployé.    
    ![Page Définir le nom de domaine complet de l’Assistant du nouveau pool frontal](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Page Définir le nom de domaine complet de l’Assistant du nouveau pool frontal")

5.  Dans la page **Sélectionner les fonctionnalités** , activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée à plusieurs, mais n’activez pas les cases à cocher Conférence rendez-vous (RTC), Voix Entreprise ou Contrôle d’admission des appels, car elles représentent les fonctionnalités de voix, de vidéo et de conférence collaborative. Pour plus d’informations sur la sélection des fonctionnalités, reportez-vous à [Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) dans la documentation de déploiement.
    
    ![Page Sélectionner les fonctionnalités du pool frontal](images/JJ205144.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Page Sélectionner les fonctionnalités du pool frontal")

6.  Dans la page **Sélectionner des rôles serveur colocalisés** , nous vous recommandons de colocaliser le serveur de médiation dans Lync Server 2013. En cas de fusion d’une topologie héritée avec Lync Server 2013, nous exigeons que vous colocalisiez d’abord le Lync Server 2010serveur de médiation. Après avoir fusionné les topologies et configuré le Lync Server 2013  serveur de médiation, vous pouvez décider de conserver le serveur de médiation colocalisé ou de le transformer en serveur autonome lorsque vous déplacez le rôle serveur de médiation vers Lync Server 2013 ultérieurement lors du processus de déploiement.
    
    ![Page Sélectionner des rôles serveur colocalisés du pool frontal](images/JJ205144.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Page Sélectionner des rôles serveur colocalisés du pool frontal")

7.  Dans la page **Rôles serveur associés à ce pool frontal** , lors du déploiement du pool pilote, ne sélectionnez pas l’option **Activer un pool Edge à utiliser avec le composant média de ce pool frontal**. Il s’agit d’une fonctionnalité que vous activerez et mettrez en ligne lors d’une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment.
    
    ![Pages Rôles serveur associés avec pool frontal](images/JJ205144.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Pages Rôles serveur associés avec pool frontal")

8.  Dans la page **Sélectionner un serveur Office Web Apps** , cliquez sur **Nouveau** , puis indiquez le nom de domaine complet du serveur d’applications.
    
    ![Définir les nouvelles propriétés du nom de domaine complet du serveur New Office Online](images/JJ205144.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Définir les nouvelles propriétés du nom de domaine complet du serveur New Office Online")

9.  Dans la page **Définir le magasin SQL Server d’archivage** , lors de la définition du magasin SQL Server pour l’archivage et la surveillance Lync Server, sélectionnez l’instance de SQL Server créée précédemment pour Lync Server 2013.
    
    ![Page Définir le magasin SQL Server d’archivage](images/JJ205144.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Page Définir le magasin SQL Server d’archivage")

10. Pour publier votre topologie, cliquez avec le bouton droit sur le nœud **Lync Server**, puis cliquez sur **Publier la topologie** .
    
    ![Générateur de topologie affichant une topologie configurée](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Générateur de topologie affichant une topologie configurée")

11. Au terme du processus, cliquez sur **Terminer** .

Pour installer une copie locale du magasin de configurations et démarrer les services requis, reportez-vous à [Configuration des serveurs et des pools frontaux pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) dans la documentation de déploiement.


