---
title: Processus de migration-détails
description: Processus de migration-détails.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569580"
---
# <a name="migration-process---details"></a>Processus de migration-détails

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Utilisez les conditions préalables et les étapes détaillées suivantes pour migrer Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat vers Lync Server 2013, serveur de conversation permanente.

<div>

## <a name="prerequisites-for-migration"></a>Conditions préalables pour la migration

Veillez à respecter les conditions préalables suivantes avant de migrer Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat vers Lync Server 2013, serveur de conversation permanente.

1.  Déployez au moins un pool Lync Server 2013. Si vous avez plusieurs pools Lync Server 2013, déterminez quel pool Lync Server 2013 sera le pool d’accueil pour le nouveau pool de serveurs Lync Server 2013 persistent chat.

2.  Installez le pool de serveurs Lync Server 2013, persistent chat. Il sera vide (pas de catégorie, de salle et de complément). Avant de migrer vos catégories, salles ou compléments hérités, vous pouvez créer des salles, des catégories ou des compléments dans votre déploiement de serveur de conversation permanente Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Notez que ces éléments nouvellement créés peuvent entrer en conflit avec les éléments hérités que vous migrez. Évitez tout conflit de nom, sans quoi ils seront remplacés à la migration des données héritées.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Préparation des données sources pour la migration

Pour préparer correctement vos données sources pour la migration, procédez comme suit.

1.  Sauvegardez les bases de données sources pour Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat. Pour plus d’informations sur la sauvegarde de SQL Server, voir « vue d’ensemble de la sauvegarde (SQL Server) » à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=254851> .
    
    <div>
    

    > [!IMPORTANT]  
    > Les services de domaine Active Directory doivent être identiques. En guise de condition de migration, vous ne pouvez pas migrer vers un pool dans un autre déploiement (en particulier dans une forêt Active Directory différente).

    
    </div>

2.  Inspectez votre configuration de catégorie Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat. Toute modification apportée à des catégories, des salles ou des compléments dans votre déploiement hérité existant sera réalisée par l’outil d’administration de conversation de groupe.
    
    <div>
    

    > [!TIP]  
    > Toute modification apportée à des catégories, des salles ou des compléments dans votre déploiement de serveur de conversation permanente Lync Server 2013 est effectuée par le panneau de configuration ou les applets de commande Windows PowerShell.

    
    </div>
    
    Pour préparer votre système hérité pour la migration, procédez comme suit.
    
    1.  Le serveur de conversation permanente prend en charge un seul niveau de catégories, contrairement à un ensemble hiérarchique profond de catégories. Après la migration, les sous-catégories sont précédées du nom complet de la catégorie parent. Vous pouvez simplifier votre structure de catégories existante afin que la structure qui en résulte satisfasse vos conditions.
    
    2.  Vérifiez les **responsables** dans la catégorie racine. Si des responsables existent à ce niveau, ces utilisateurs seront ajoutés en tant que **responsables de toutes les salles** après la migration. S’il ne s’agit pas d’un impératif pour votre organisation, vous devez supprimer ces responsables de la catégorie racine.
    
    3.  Vérifiez la longueur des noms de salle. Après la migration, en raison des structures de catégories simplifiées, si les salles existent sous une catégorie enfant, elles sont précédées du nom complet de la catégorie parent. Les noms peuvent inclure jusqu’à 256 caractères (nom de la catégorie parent inclus). Vous devez vérifier la longueur des noms de salle et éventuellement les raccourcir s’ils sont trop longs.
    
    4.  Dans Lync Server 2013, si les paramètres des **invitations** aux catégories sont définis sur true, vous pouvez choisir true ou false pour les invitations à des salles sous cette catégorie. Cependant, si les paramètres des invitations de catégorie sont définis sur false, les invitations des salles sous cette catégorie sont désactivées. Avant la migration, vous devez réinitialiser les paramètres d’invitation dans votre version héritée du serveur de conversation de groupe Lync Server si vous voulez que des salles soient présentes dans une catégorie spécifique. Dans le cas contraire, lors de la migration, Lync Server 2013 affiche des avertissements et définit les salles sur la valeur par défaut false.
    
    5.  Si vous avez utilisé des fichiers dans des salles de conversation, vous devez restaurer manuellement les fichiers dans le nouveau magasin de fichiers de conversation permanente après la migration. Les outils ne le font pas.
    
    6.  Si vous aviez des utilisateurs fédérés et des salles avec des utilisateurs fédérés, sachez que le serveur de conversation permanente ne prend pas en charge la Fédération. Les salles avec des utilisateurs fédérés seront migrées ; Toutefois, les utilisateurs eux-mêmes ne pourront pas accéder au contenu, car l’accès fédéré n’est pas pris en charge.
    
    7.  Identifiez les salles que vous ne voulez pas migrer, et marquez-les comme désactivées.
    
    8.  Spécifiez la date après laquelle vous voulez migrer le contenu des salles de conversation. Par exemple, vous pouvez exclure les messages antérieurs au 1er janvier 2010 de la migration, car ceux-ci sont obsolètes ou non appropriés pour la migration.

</div>

<div>

## <a name="performing-the-migration"></a>Exécution de la migration

Effectuez les étapes suivantes pour migrer votre serveur de conversation de groupe hérité.

1.  Arrêtez les services Lync Server 2010, conversation de groupe, conversation de groupe Office Communications Server 2007 R2 ou Lync Server 2013, serveur de conversation permanente. Tous les services doivent être arrêtés, aussi, devez-vous planifier cette opération à un moment opportun. Comme décrit précédemment, veillez à sauvegarder votre base de données de conversation de groupe actuelle.

2.  Exécutez la cmdlet Windows PowerShell **Export-applet cspersistentchatdata** en tant que membre du rôle RBAC de l’administrateur de conversation permanente (CsPersistentChatAdministrator). Pour plus d’informations sur les applets de commande d’exportation/importation, voir [Troubleshooting persistent Chat Server Configuration Using Windows PowerShell Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Inspectez le contenu exporté.

3.  Avant d’être prêt à importer, arrêtez Lync Server 2013 et les services de serveur de conversation permanente. Tous les services doivent être arrêtés, aussi, devez-vous planifier cette opération à un moment opportun.

4.  Effectuez une sauvegarde de la base de données de conversation permanente si vous avez créé des catégories, des salles ou des compléments dans votre déploiement Lync Server 2013 avant la migration. Le processus d’exportation/importation sera en mesure de fusionner les données héritées dans le déploiement Lync Server 2013, mais vous souhaiterez sauvegarder la base de données si le contenu est remplacé par inadvertance (par exemple, en cas de conflits d’affectation de noms).

5.  Exécutez l’applet de commande **Import-applet cspersistentchatdata** Windows PowerShell (outil d’importation), avec une commande **WhatIf** pour remplir le serveur principal du pool de serveurs de conversation permanente avec les données migrées. Certaines conversions surviennent dans le processus pour prendre en charge le modèle d’administration simplifié. Corrigez les erreurs et avertissements qui apparaissent.

6.  Exécutez la cmdlet Windows PowerShell **Import-applet cspersistentchatdata** du serveur de conversation permanente en tant que membre du rôle RBAC de l’administrateur de conversation permanente (CsPersistentChatAdministrator). Pour plus d’informations sur les applets de commande d’exportation/importation, voir [Troubleshooting persistent Chat Server Configuration Using Windows PowerShell Cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  Vous devez XCOPY tous les fichiers téléchargés (tout le dossier) vers le nouveau magasin de fichiers de conversation permanente Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Le Lync 2013 (client) ne prend pas en charge le téléchargement ou l’affichage de fichiers dans les salles de conversation. Vous pouvez toujours utiliser le client hérité pour publier et afficher les fichiers dans la salle.

    
    </div>

8.  Transférez l’URI du serveur de recherche de conversation de groupe Lync Server 2010, Group chat ou Office Communications Server 2007 R2 vers l’objet contact de serveur de conversation permanente Lync Server 2013. Les étapes suivantes sont requises si votre client Lync 2010 Group chat ou Office Communicator 2007 R2 Group chat doit se connecter à la dernière version de Lync 2013, persistent chat (client) après la migration sans modification de configuration côté client :
    
      - Supprimez le \<domainName\> compte d’utilisateur du serveur de recherche OCSChat@. com. Il a été utilisé pour pointer vers le service de recherche dans Lync Server 2010, Group chat. Vous pouvez désinstaller le pool et supprimer les entrées approuvées plus tard.
    
      - Créez un point de terminaison hérité (objet contact de serveur de conversation permanente) en exécutant l’applet de commande Windows PowerShell, **New-CsPersistentChatEndpoint**, avec l’URI SIP identique afin que le client hérité fonctionne correctement lors du redémarrage du service.
    
    Le processus de migration obligatoire est terminé à ce point. Lync 2010 Group chat (clients) ou Office Communicator 2007 R2 Group chat (clients) peuvent se connecter au nouveau pool de serveurs de conversation permanente maintenant, de façon transparente.
    
    Suivez ces étapes de désaffectation supplémentaires pour Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat.

9.  Démarrez les services du serveur de conversation permanente en activant tous les ordinateurs dans le nouveau pool de serveurs de conversation permanente.

10. Utilisez le panneau de configuration Lync Server et les applets de commande Windows PowerShell pour vérifier que les données ont été correctement migrées.

11. Désinstallez Lync 2010 Group chat ou Office Communicator 2007 R2 Group chat des ordinateurs du pool de serveurs de conversation de groupe.

12. Supprimez l’application approuvée et le pool d’applications approuvées à l’aide des applets de commande Windows PowerShell. Ces éléments sont supprimés du magasin central de gestion et des entrées de service approuvé associées (est) à partir d’Active Directory. Cette étape peut également être utilisée à l’aide du générateur de topologie (les pools et les applications approuvées ont un nœud dédié, également).

13. Vous pouvez maintenant commencer à activer la fonctionnalité de serveur de conversation permanente via les nouveaux clients. Pour plus d’informations sur l’activation du serveur de conversation permanente, voir [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 prend en charge plusieurs pools de serveurs de conversation permanente. Toutefois, nous prenons en charge la migration d’un pool Lync 2010 Group chat ou Office Communications Server 2007 R2 &nbsp; Group chat vers un pool de serveurs de conversation permanente et Lync server 2013. Vous pouvez ajouter des pools de serveurs de conversation permanente dans votre déploiement pour répondre aux besoins de réglementation (par exemple, conserver des données au sein d’une géographie donnée).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

