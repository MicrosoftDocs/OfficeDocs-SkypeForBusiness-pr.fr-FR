---
title: Processus de migration - Détails
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Processus de migration - Détails

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Pour migrer vers Lync Server 2013, le serveur de chat permanent, vous devez disposer des éléments requis suivants et des étapes détaillées de migration de Lync Server 2010, de discussion de groupe ou d’Office Communications Server 2007 R2.

<div>

## <a name="prerequisites-for-migration"></a>Conditions préalables à la migration

Assurez-vous que vous remplissez les conditions préalables suivantes avant de procéder à la migration de Lync Server 2010, d’une conversation de groupe ou d’une conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, serveur de chat permanent.

1.  Déploiement d’au moins un pool Lync Server 2013. Si vous avez plusieurs pools Lync Server 2013, déterminez le pool Lync Server 2013, le pool Home pour le nouveau pool Lync Server 2013 Chat Server.

2.  Installez Lync Server 2013, le pool de serveurs de chat permanent. Il sera vide (aucune catégorie, salle ou complément). Avant de migrer vos catégories, salles ou compléments hérités, vous pouvez créer des salles, des catégories ou des compléments dans votre Lync Server 2013, le déploiement permanent du serveur Chat.
    
    <div>
    

    > [!IMPORTANT]  
    > Gardez à l’esprit que ces éléments nouvellement créés risquent de entrer en conflit avec des éléments hérités que vous migrez. Éviter les conflits de noms; Sinon, ils sont écrasés lors de la migration des données héritées.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Préparation des données sources pour la migration

Suivez les étapes ci-dessous pour préparer correctement vos données sources pour la migration.

1.  Sauvegardez les bases de données sources pour Lync Server 2010, les discussions de groupe ou les discussions de groupe Office Communications Server 2007 R2. Pour plus d’informations sur la façon de sauvegarder SQL Server, voir «vue d’ensemble de la <http://go.microsoft.com/fwlink/p/?linkid=254851>sauvegarde (SQL Server)».
    
    <div>
    

    > [!IMPORTANT]  
    > Les services de domaine Active Directory doivent être identiques. Dans le cadre de la migration, vous ne pouvez pas effectuer de migration vers un pool dans un autre déploiement (plus précisément dans une autre forêt Active Directory).

    
    </div>

2.  Inspectez votre Lync Server 2010, vos discussions de groupe ou les salles de conversation de groupe et la configuration des catégories de Lync Server 2007 R2. Toute modification apportée à des catégories, des salles ou des compléments dans votre déploiement hérité actuel est réalisée par l’outil d’administration de discussion de groupe.
    
    <div>
    

    > [!TIP]  
    > Toute modification apportée à des catégories, des salles ou des compléments dans votre Lync Server 2013, le déploiement de serveur de chat permanent est effectué par le panneau de configuration de Lync Server ou les applets de commande Windows PowerShell.

    
    </div>
    
    Suivez ces étapes pour préparer votre système hérité à des fins de migration.
    
    1.  Le serveur Chat permanent prend en charge un seul niveau de catégories, contrairement à un ensemble hiérarchique de catégories. Après la migration, les sous-catégories sont préfixées avec les noms de catégorie parents complets. Vous voudrez peut-être simplifier et aplatir votre structure de catégorie existante pour que la structure qui en résulte réponde à vos besoins.
    
    2.  Vérifiez les **responsables** de la catégorie racine. S’il existe des gestionnaires à ce niveau, ces utilisateurs seront ajoutés comme **responsables à toutes les pièces** après la migration. Si ce n’est pas une obligation pour votre organisation, vous devez supprimer ces responsables de la catégorie racine.
    
    3.  Vérifiez la longueur des noms de salle. Après la migration, en raison de la présence de structures de catégories simplifiées, les noms de catégorie parent complet sont préfixés. La limite d’appellation est de 256 caractères, y compris les noms de catégorie parent. Vous devez vérifier la longueur des noms de la salle et, éventuellement, réduire sa longueur, s’il est trop long.
    
    4.  Dans Lync Server 2013, si les paramètres **** d’invitations de catégorie sont définis sur true, vous pouvez choisir true ou false pour les invitations aux salles de cette catégorie. Toutefois, si les paramètres d’invitations de la catégorie sont définis sur false, les invitations sont désactivées. Avant de procéder à la migration, vous devez réinitialiser les paramètres d’invitation dans votre version du serveur de conversation de groupe Lync Server héritée, si vous souhaitez que la salle (s) existe dans une catégorie spécifique. Dans le cadre de la migration, Lync Server 2013 affiche les avertissements et définit les salles sur la valeur par défaut false.
    
    5.  Si vous avez utilisé des fichiers dans des salles de conversation, vous devez restaurer manuellement les fichiers dans le nouveau magasin de fichiers de chat permanent après la migration. Ce n’est pas le cas pour les outils.
    
    6.  Si vous aviez des utilisateurs fédérés et des salles avec des utilisateurs fédérés, sachez que le serveur Chat permanent ne prend pas en charge la Fédération. Les salles avec des utilisateurs fédérés seront migrées; Toutefois, les utilisateurs ne seront pas en mesure d’accéder au contenu, car l’accès fédéré n’est pas pris en charge.
    
    7.  Identifiez les salles que vous ne souhaitez pas migrer et marquez-les comme désactivées.
    
    8.  Déterminez la date au-delà de laquelle vous souhaitez migrer le contenu de la salle de conversation. Par exemple, il est possible que vous ne souhaitiez pas migrer des messages antérieurs au 1er janvier 2010, car ces messages risquent d’être obsolètes ou non pertinents pour la migration.

</div>

<div>

## <a name="performing-the-migration"></a>Exécution de la migration

Suivez les étapes ci-dessous pour migrer votre serveur de discussion de groupe hérité.

1.  Arrêtez le serveur Lync Server 2010, les discussions de groupe, les discussions de groupe Office Communications Server 2007 R2 ou Lync Server 2013, services de chat permanent. Tous les services doivent être arrêtés, donc envisagez d’y parvenir à un moment où le temps d’arrêt est suffisant. Comme décrit précédemment, assurez-vous de sauvegarder votre base de données de discussion de groupe actuelle.

2.  Exécutez l’applet de la cmdlet Windows PowerShell **Export-CsPersistentChatData** en tant que membre du rôle RBAC administrateur de chat permanent (CsPersistentChatAdministrator). Pour plus d’informations sur les applets de connexion d’exportation et d’importation, voir [résolution des problèmes de configuration du serveur de chat permanent au moyen des cmdlets Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Inspectez le contenu exporté.

3.  Avant de pouvoir procéder à l’importation, fermez Lync Server 2013 et les services serveur de chat permanent. Tous les services doivent être arrêtés, donc envisagez d’y parvenir à un moment où le temps d’arrêt est suffisant.

4.  Effectuez une sauvegarde de la base de données de chat permanent si vous avez créé des catégories, des salles ou des compléments dans votre déploiement Lync Server 2013 avant la migration. Le processus d’exportation/importation est en mesure de fusionner les données héritées dans le déploiement de Lync Server 2013, mais il est préférable de sauvegarder la base de données au cas où le contenu serait involontairement écrasé (par exemple, en cas de conflit d’attribution de noms).

5.  Exécutez l’applet de commande Windows PowerShell **Import-CsPersistentChatData** (outil d’importation), avec une commande **WhatIf** pour remplir le serveur principal du pool de serveurs de chat permanent avec les données déplacées. Certaines conversions se produisent dans le processus pour s’adapter au modèle d’administration simplifié. Corrigez les erreurs ou avertissements qui s’affichent.

6.  Exécutez l’applet de la cmdlet Windows PowerShell **Import-CsPersistentChatData** en tant que membre du rôle RBAC de l’administrateur de chat permanent (CsPersistentChatAdministrator). Pour plus d’informations sur les applets de connexion d’exportation et d’importation, voir [résolution des problèmes de configuration du serveur de chat permanent au moyen des cmdlets Windows PowerShell dans Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Vous devez enregistrer tous les fichiers téléchargés (le dossier complet) sur le nouveau Lync Server 2013, magasin de fichiers de conversation permanent.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (client) ne prend pas en charge le chargement ou l’affichage de fichiers dans des salles de conversation. Vous pouvez toujours utiliser le client hérité pour publier et afficher des fichiers dans la salle.

    
    </div>

8.  Sur le port de Lync Server 2010, de discussion de groupe ou d’Office Communications Server 2007 R2, le serveur de recherche de discussion de groupe sur Lync Server 2013, objet de contact du serveur de conversation permanent Les étapes suivantes sont nécessaires si votre discussion de groupe Lync 2010 ou les clients de conversation de groupe Office Communicator 2007 R2 doivent se connecter à la dernière version de Lync 2013, de conversation permanente (client) après la migration sans modification de configuration côté client:
    
      - Supprimez le compte\<d'\>utilisateur du serveur de recherche OCSChat @ nom_domaine. com. Il a été utilisé pour pointer vers le service de recherche dans Lync Server 2010, discussion de groupe. Vous pouvez désinstaller le pool et supprimer les entrées approuvées ultérieurement.
    
      - Créer un point de terminaison hérité (objet de contact de chat permanent) en exécutant l’applet de cmdlet Windows PowerShell, **New-CsPersistentChatEndpoint**, avec l’URI SIP identique de sorte que le client hérité puisse fonctionner efficacement au redémarrage du service.
    
    Le processus de migration obligatoire est terminé à ce stade. Les discussions de groupe Lync 2010 (clients) ou les discussions de groupe Office Communicator 2007 R2 (clients) peuvent se connecter au nouveau pool de serveurs de chat permanent désormais, de manière transparente.
    
    Suivez ces étapes supplémentaires de désaffectation pour Lync Server 2010, les discussions de groupe ou la discussion de groupe Office Communications Server 2007 R2.

9.  Démarrez les services serveur de chat permanent en activant tous les ordinateurs du nouveau pool de serveurs de chat permanent.

10. Utilisez les applets de commande du panneau de configuration de Lync Server et de Windows PowerShell pour vérifier que les données ont bien été déplacées.

11. Désinstallez la discussion de groupe Lync 2010 ou la discussion de groupe Office Communicator 2007 R2 sur les ordinateurs du pool de serveurs de discussion de groupe.

12. Supprimez l’application approuvée et le pool d’applications approuvé à l’aide de cmdlets Windows PowerShell. Cela supprime les éléments suivants du magasin de gestion central et des entrées de service de confiance associées dans Active Directory. Par ailleurs, cette étape fonctionne à l’aide du générateur de topologie (les applications/pools approuvés disposent également d’un nœud dédié).

13. Vous pouvez à présent commencer à activer la fonctionnalité serveur de chat permanent par le biais des nouveaux clients. Pour plus d’informations sur l’activation d’un serveur de chat permanent, voir [déploiement d’un serveur de chat permanent dans Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 prend en charge plusieurs pools de serveurs de chat permanent. Néanmoins, nous prenons en charge la migration d’une conversation de groupe Lync 2010 ou&nbsp;d’une liste de discussion de groupe Office Communications Server 2007 R2 vers une seule Lync Server 2013, un pool de serveurs de chat permanent. Vous pouvez ajouter des regroupements de serveurs de chat permanents supplémentaires dans votre déploiement pour répondre aux besoins en matière de réglementation (par exemple, conservation des données au sein d’une géographie donnée).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

