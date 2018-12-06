---
title: Déploiement du pool pilote Lync Server 2013
TOCTitle: Déploiement du pool pilote Lync Server 2013
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204718(v=OCS.15)
ms:contentKeyID: 49296403
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement du pool pilote Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-22_

L’une des premières étapes requises pour la migration Lync Server 2013 consiste à déployer un pool pilote. Un pool pilote correspond à l’endroit auquel vous testez la coexistence de Lync Server 2013 avec votre déploiement de Office Communications Server 2007 R2. La coexistence est un état temporaire qui dure jusqu’à ce que vous déplaciez l’ensemble des utilisateurs et des pools vers Lync Server 2013.

Lorsque vous déployez un pool pilote, vous utilisez l’Assistant Définir un nouveau pool frontal. Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool pilote Lync Server 2013 que dans votre pool Office Communications Server 2007 R2. Si vous avez déployé un serveur d’archivage, un serveur de surveillance ou un System Center Operations Manager pour l’archivage ou la surveillance de votre environnement Office Communications Server 2007 R2 et que vous souhaitez une continuité de l’archivage et de la surveillance tout au long de la migration, vous devez également déployer ces fonctionnalités dans votre environnement pilote. La version que vous avez déployée pour archiver et surveiller votre environnement Office Communications Server 2007 R2 ne capture pas de données dans votre environnement Lync Server 2013.

> [!NOTE]  
> La procédure qui suit traite des fonctionnalités et paramètres à considérer dans le cadre du processus de déploiement général de votre pool pilote. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour en connaître les étapes précises, reportez-vous au guide de déploiement intitulé <a href="lync-server-2013-deploying-lync-server.md">Déploiement de Lync Server 2013</a>.

**Pour déployer un pool pilote Lync Server 2013**

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Ouvrez le générateur de topologie et créez une nouvelle topologie.

3.  Entrez le domaine SIP principal.
    
    ![Créer une topologie, page Définir le domaine principal](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Créer une topologie, page Définir le domaine principal")

4.  Poursuivez les étapes de l’Assistant jusqu’à l’ouverture de l’Assistant **Définir le nouveau pool frontal**. Cliquez sur Suivant.

5.  Entrez le nom de domaine complet du pool. Lorsque vous définissez votre pool pilote, vous pouvez choisir de déployer un pool de serveurs frontaux Enterprise Edition ou un serveur Standard Edition. Lync Server 2013 n’exige pas que les fonctionnalités de votre pool pilote correspondent à celles déployées dans votre pool hérité.
    
    > [!WARNING]  
    > Le nom de domaine complet du pool ou serveur que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool Office Communications Server 2007 R2 actuellement déployé ni à tout autre serveur actuellement déployé.    
    ![Page Définir le nom de domaine complet du pool frontal](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Page Définir le nom de domaine complet du pool frontal")

6.  Définissez l’ordinateur qui va être ajouté au pool.
    
    ![Boîte de dialogue Définir un nouveau pool frontal](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Boîte de dialogue Définir un nouveau pool frontal")

7.  Dans la page **Sélectionner les fonctionnalités** , activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée à plusieurs, mais n’activez pas les cases à cocher Conférence rendez-vous (RTC), Voix Entreprise ou Contrôle d’admission des appels, car elles représentent les fonctionnalités de voix, de vidéo et de conférence collaborative. Pour plus d’informations sur la sélection des fonctionnalités, reportez-vous à [Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) dans la documentation de déploiement.
    
    ![Page Sélectionner les fonctionnalités du pool frontal](images/JJ205144.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Page Sélectionner les fonctionnalités du pool frontal")

8.  Dans la page **Sélectionner des rôles serveur colocalisés**, nous vous recommandons de colocaliser le serveur de médiation dans Lync Server 2013. En cas de fusion d’une topologie héritée avec Lync Server 2013, nous exigeons que vous colocalisiez d’abord le Office Communications Server 2007 R2serveur de médiation. Une fois les topologies fusionnées et le Lync Server 2013serveur de médiation configuré, vous pouvez décider de conserver le serveur de médiation colocalisé ou de le transformer en serveur autonome lorsque vous déplacez ultérieurement le rôle serveur de médiation vers Lync Server 2013 lors du processus de déploiement.
    
    ![Page Sélectionner des rôles serveur colocalisés du pool frontal](images/JJ205144.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Page Sélectionner des rôles serveur colocalisés du pool frontal")

9.  Dans la page **Rôles serveur associés à ce pool frontal** , lors du déploiement du pool pilote, ne sélectionnez pas l’option **Activer un pool Edge à utiliser avec le composant média de ce pool frontal**. Il s’agit d’une fonctionnalité que vous activerez et mettrez en ligne lors d’une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment.
    
    ![Pages Rôles serveur associés avec pool frontal](images/JJ205144.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Pages Rôles serveur associés avec pool frontal")

10. Dans la page **Sélectionner un serveur Office Web Apps** , cliquez sur **Nouveau** , puis indiquez le nom de domaine complet du serveur d’applications.
    
    ![Définir les nouvelles propriétés du nom de domaine complet du serveur New Office Online](images/JJ205144.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Définir les nouvelles propriétés du nom de domaine complet du serveur New Office Online")

11. Dans la page **Définir le magasin SQL Server d’archivage** , sélectionnez l’instance SQL Server créée précédemment pour Lync Server 2013.
    
    ![Page Définir le magasin SQL Server d’archivage](images/JJ205144.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Page Définir le magasin SQL Server d’archivage")

12. Dans la page **Définir le magasin SQL Server pour la surveillance** , sélectionnez l’instance SQL Server créée précédemment pour Lync Server 2013. Cliquez sur **Terminer**.

13. Dans le nœud supérieur du générateur de topologie, cliquez avec le bouton droit sur **Lync Server**, puis cliquez sur **Modifier les propriétés**. Cliquez sur **URL simples**.

14. Mettez à jour l’**URL d’accès administratif**.
    
    ![Modifier les propriétés, page URL simples](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Modifier les propriétés, page URL simples")
    
    Pour plus d’informations sur les URL simples, reportez-vous à la rubrique [Modification ou configuration des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) dans la documentation de déploiement.

15. Dans **Modifier les propriétés**, cliquez sur **Serveur de gestion centralisée**.

16. Dans la liste déroulante, sélectionnez le pool Lync Server 2013.
    
    ![Modifier les propriétés, page serveur de gestion centralisée](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Modifier les propriétés, page serveur de gestion centralisée")

17. Cliquez sur OK pour fermer la page **Modifier les propriétés**.

18. Dans le menu **Action**, sélectionnez **Publier la topologie**.

19. Au terme du processus, cliquez sur **Terminer** .

20. De retour dans l’Assistant de déploiement de Lync Server 2013, cliquez sur **Installer ou mettre à jour le système Lync Server**.
    
    ![Assistant Déploiement Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Assistant Déploiement Lync Server 2013")

Pour installer une copie locale du magasin de configurations et démarrer les services requis, reportez-vous à [Configuration des serveurs et des pools frontaux pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) dans la documentation de déploiement.


