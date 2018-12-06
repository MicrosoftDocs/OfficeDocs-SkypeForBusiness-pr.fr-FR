---
title: "Lync Server 2013 : Ajout d’un serv. de conv. permanente à la topologie"
TOCTitle: Ajout d’un serveur de conversation permanente à la topologie
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205049(v=OCS.15)
ms:contentKeyID: 49297916
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout d’un serveur de conversation permanente à la topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Vous devez incorporer la prise en charge de serveur de conversations permanentesLync Server 2013, dans votre topologie avant de pouvoir configurer votre déploiement pour qu’il prenne en charge un serveur de conversations permanentes. Les informations de cette rubrique décrivent comment utiliser le Générateur de topologie pour ajouter la prise en charge serveur de conversations permanentes à votre topologie existante.

## Pour ajouter un serveur de conversations permanentes à une topologie

Exécutez les étapes suivantes pour installer un pool de serveurs de conversations permanentes sans configurer la récupération d’urgence. Pour configurer un pool de serveurs de conversations permanentes étiré pour une haute disponibilité et la récupération d’urgence, reportez-vous à [Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation du déploiement.

Pour déployer plusieurs pools de serveurs de conversations permanentes, répétez la même procédure pour chaque pool.

1.  Sur un ordinateur exécutant Lync Server 2013 ou disposant des outils d’administration de Lync Server, ouvrez une session à l’aide d’un compte membre du groupe local Utilisateurs (ou disposant de droits d’utilisateur équivalents).
    
    > [!NOTE]  
    > Vous pouvez définir une topologie en utilisant un compte membre du groupe local Utilisateurs, mais pour publier une topologie, ce qui nécessite l’installation d’un serveur Lync Server 2013, vous devez utiliser un compte membre du groupe <strong>Administrateurs du domaine</strong> et du groupe <strong>RTCUniversalServerAdmins</strong>, qui dispose des autorisations de contrôle total (c’est-à-dire, lecture, écriture et modification) sur le magasin de fichiers que vous allez utiliser pour le magasin de fichiers du serveur de conversations permanentes (afin que le Générateur de topologie puisse configurer les DACL requises), ou un compte avec des droits équivalents.

2.  Démarrez le Générateur de topologie.

3.  Dans l’arborescence de la console, accédez au nœud **conversation permanente Pools**, puis développez-le pour sélectionner un pool de serveurs de conversations permanentes, ou cliquez avec le bouton droit et choisissez **Nouveau pool conversation permanente**. Vous devez définir le nom de domaine complet (FQDN) du pool et indiquer si le pool sera un déploiement de pool à serveur unique ou à plusieurs serveurs.
    
    Vous pouvez choisir un **Pool de plusieurs ordinateurs** ou un **Pool d’un seul ordinateur** . Choisissez le premier si vous prévoyez d’utiliser plusieurs serveur frontal de serveur de conversations permanentes dans votre pool de serveurs de conversations permanentes. Effectuez ce choix maintenant, ou ultérieurement, car une fois créé un pool d’un seul ordinateur, vous ne pourrez pas ajouter d’autres serveurs. Si vous choisissez un pool de plusieurs ordinateurs, entrez les noms des serveurs frontauxserveur de conversations permanentes individuels qui composent le pool.
    
    > [!IMPORTANT]  
    > Si le rôle serveur de conversations permanentes est installé sur un serveur Standard EditionLync Server 2013, le nom de domaine complet doit correspondre à celui du serveur Standard Edition.

4.  Définissez un **Nom d’affichage** simple pour le pool de serveurs de conversations permanentes. Ce nom d’affichage peut être utilisé par des clients personnalisés, tout spécialement quand il existe plusieurs pools de serveurs de conversations permanentes afin de différencier les salles.

5.  Définissez le port utilisé par le serveur de conversations permanentes pour communiquer avec les serveurs frontauxLync Server. Le port par défaut est 5041.

6.  Si votre organisation nécessite la prise en charge de la conformité, cochez la case **Activer la conformité** . Si cette option est sélectionnée, le service Conformité du serveur de conversations permanentes est installé sur le même ordinateur que le serveur frontalserveur de conversations permanentes. Vous devez sélectionner un SQL Serverserveur principal pour la conformité du serveur de conversations permanentes ultérieurement.

7.  Attribuez l’affinité de site pour le pool de serveurs de conversations permanentes. Cochez la case **Utiliser ce pool par défaut pour le site \<nom\_site\>** ou **Toujours utiliser ce pool pour tous les sites** pour désigner ce pool de serveurs de conversations permanentes comme pool par défaut pour le site actuel ou tous les sites. Quand le client Lync 2013 est utilisé pour créer et gérer les salles, le pool par défaut associé au site de l’utilisateur est utilisé pour la création et la gestion de la salle afin de pouvoir acheminer les opérations de création et de gestion de salle vers ce pool. Cela s’applique uniquement quand vous avez plusieurs pools de serveurs de conversations permanentes déployés, et que vous voulez utiliser les fonctionnalités de création et de gestion de salle du serveur de conversations permanentes.
    
    > [!IMPORTANT]  
    > Vous pouvez personnaliser les fonctionnalités de création et de gestion de salle à l’aide du Kit de développement logiciel (SDK) serveur de conversations permanentes.<br />
    Pour des informations sur la configuration des bases de données de sauvegarde SQL Server pour la récupération d’urgence, reportez-vous à <a href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</a> dans la documentation de déploiement.

8.  Définissez le **Magasin SQL pour le serveur frontal serveur de conversations permanentes (endroit où le contenu d’une salle de conversation est stocké)** en procédant ainsi :
    
      - Pour utiliser une base de données SQL Server existante, dans la liste déroulante, cliquez sur le nom de la base de données SQL Server que vous voulez utiliser.
    
      - Pour spécifier une nouvelle base de données SQL Server, cliquez **Nouveau** , et dans **Définir un nouveau magasin SQL** , procédez ainsi :
    
    <!-- end list -->
    
      - Dans **Nom de domaine complet du serveur SQL Server** , indiquez le nom de domaine complet du SQL Server sur lequel vous voulez créer la nouvelle base de données SQL Server.
    
      - Sélectionnez **Instance par défaut** pour utiliser l’instance par défaut ou, pour spécifier une autre instance, sélectionnez **Instance nommée** , et spécifiez l’instance que vous voulez utiliser.

9.  Définissez la base de données de conformité SQL Server si vous avez activé la conformité.
    
    > [!IMPORTANT]  
    > Pour des informations sur la configuration des miroirs SQL Server pour une haute disponibilité pour la base de données du serveur de conversations permanentes et la base de données de conformité du serveur de conversations permanentes, reportez-vous à <a href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</a> dans la documentation de déploiement.

10. Définissez le magasin de fichiers. Un magasin de fichiers est un dossier dans lequel une copie des fichiers téléchargés dans le référentiel est stockée (par exemple, le stockage des pièces jointes publiées dans une salle de conversation). Dans le cas d’une topologie de serveur de conversations permanentes à plusieurs serveurs, il doit s’agir d’un chemin UNC, et pour une topologie de serveur de conversations permanentes à un seul serveur, il s’agit d’un chemin local.
    
    Pour utiliser un magasin de fichiers existant, procédez ainsi :
    
      - Dans **Nom de domaine complet du serveur de fichiers** , indiquez le nom de domaine complet du magasin de fichiers dans lequel vous voulez créer le nouveau magasin de fichiers.
    
      - Dans **Partage de fichiers** , indiquez le magasin de fichiers à utiliser.
    
    > [!IMPORTANT]  
    > Vous pouvez définir le magasin de fichiers dans le Générateur de topologie avant de créer le magasin de fichiers, mais vous devez créer le magasin de fichiers dans l’emplacement défini avant de publier la topologie.

11. Sélectionnez le pool de serveur frontal à utiliser au tronçon suivant pour ce pool de serveurs de conversations permanentes. Il s’agit du pool de serveur frontal qui acheminera les demandes du serveur de conversations permanentes vers ce pool.

12. Pour enregistrer la configuration, cliquez sur **Terminer** . Le pool de serveurs de conversations permanentes s’affiche dans le Générateur de topologie avec les paramètres de pool spécifiques.
    
    Pour publier la topologie mise à jour pour laquelle vous avez serveur de conversations permanentes, reportez-vous à [Publication de la topologie mise à jour dans Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) dans la documentation du déploiement.
    
    > [!NOTE]  
    > Quand le Générateur de topologie est ouvert, vous pouvez passer à l’étape 3 de <a href="lync-server-2013-publish-the-updated-topology.md">Publication de la topologie mise à jour dans Lync Server 2013</a> pour commencer à publier votre topologie mise à jour.
