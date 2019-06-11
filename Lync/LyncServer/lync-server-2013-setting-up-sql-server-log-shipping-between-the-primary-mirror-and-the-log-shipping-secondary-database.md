---
title: 'Lync Server 2013 : Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire de copie des journaux de transaction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire de copie des journaux de transaction dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Pour continuer, procédez comme suit pour l’envoi de journaux dans le cas où la base de données de chat persistante principale a basculé vers sa base de données miroir.

1.  Basculez manuellement vers le miroir sur la base de données de conversation persistante principale. Pour ce faire, vous utilisez Lync Server Management Shell et l’applet **de passe Invoke-CsDatabaseFailover** . Pour plus d’informations, reportez-vous à la section «utilisation des cmdlets Lync Server Management Shell» du [déploiement de la mise en miroir SQL pour la haute disponibilité du serveur principal dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  À l’aide de SQL Server Management Studio, connectez-vous à l’instance de miroir du serveur de chat permanent principal.

3.  Assurez-vous que l’agent SQL Server est en cours d’exécution.

4.  Cliquez avec le bouton droit sur la base de données mgc, puis cliquez sur **Propriétés**.

5.  Sous **Sélectionner une page**, cliquez sur **Envoi des journaux de transactions**.

6.  Activez la case à cocher **Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**.

7.  Sous **Sauvegardes des journaux de transactions**, cliquez sur **Paramètres de sauvegarde**.

8.  Dans la zone **Indiquer le chemin d’accès réseau au dossier de sauvegarde**, tapez le chemin d’accès réseau du partage que vous avez créé pour le dossier de sauvegarde du journal des transactions.

9.  Si le dossier de sauvegarde se trouve sur le serveur principal, tapez le chemin d’accès local au dossier de sauvegarde dans la zone **Si le dossier de sauvegarde se trouve sur le serveur principal, tapez un chemin d’accès local au dossier**. (Si le dossier de sauvegarde ne figure pas sur le serveur principal, vous pouvez laisser cette case à cocher vide.)
    
    <div>
    

    > [!IMPORTANT]  
    > Si le compte de service SQL Server sur votre serveur principal s’exécute sous le compte système local, vous devez créer votre dossier de sauvegarde sur le serveur principal et spécifier un chemin local vers ce dossier.

    
    </div>

10. Configurez les paramètres **Supprimer les fichiers antérieurs à** et **Envoyer une alerte si aucune sauvegarde ne se produit en l’espace de**.

11. Examinez la planification des sauvegardes dans la zone **Planification** sous **Travail de sauvegarde**. Pour personnaliser le planning de votre installation, cliquez sur **Planning**, puis ajustez la planification de l’agent SQL Server, selon les besoins.
    
    <div>
    

    > [!IMPORTANT]  
    > Utilisez les mêmes paramètres que ceux de la base de données primaire.

    
    </div>

12. Sous **Compression**, sélectionnez **Utiliser le paramètre du serveur par défaut**, puis cliquez sur **OK**.

13. Sous **Instances de serveurs et bases de données secondaires**, cliquez sur **Ajouter**.

14. Cliquez sur **Connexion**, puis connectez-vous à l’instance de SQL Server que vous avez configurée en tant que serveur secondaire.

15. Dans la zone **Base de données secondaire** sélectionnez la base de données **mgc** dans la liste.

16. Sous l’onglet **Initialiser la base de données secondaire**, sélectionnez l’option **Non, la base de données secondaire est initialisée**.

17. Sous l’onglet **Copier les fichiers**, dans **Dossier de destination des fichiers copiés**, tapez le chemin d’accès du dossier dans lequel les sauvegardes des journaux de transactions doivent être copiées, puis cliquez sur **OK**. Ce dossier est souvent situé sur le serveur secondaire.

18. Ouvrez la liste déroulante **Créer un script de configuration**, puis sélectionnez **Créer un script de configuration dans une nouvelle fenêtre de requête**.

19. Dans la nouvelle fenêtre de requête, dans **Propriétés de la base de données**, cliquez sur **OK** pour commencer le processus de configuration.

20. Sélectionnez et exécutez la première moitié de la requête (Voir l’étape 18) jusqu’à la ligne:- \* \* \* \* \* \* -end: script à exécuter sur le principal \* \* \* \* \* \*:.
    
    <div>
    

    > [!IMPORTANT]  
    > L’exécution manuelle de ce script est nécessaire car SQL Server Management Studio ne prend pas en charge plusieurs bases de données principales dans une configuration d’envoi du journal SQL Server.

    
    </div>

21. Sélectionnez **Annuler** pour fermer le panneau de configuration de copie des journaux de transaction et établir une configuration de travail qui implémente correctement la copie des journaux de transaction pour la base de données primaire et la base de données en miroir (en cas de basculement). 

22. Restaurez manuellement la base de données de conversation persistante principale sur le serveur principal. Pour ce faire, utilisez Lync Server Management Shell et l’applet **de passe Invoke-CsDatabaseFailover** . Pour plus d’informations, reportez-vous à la section «utilisation des cmdlets Lync Server Management Shell» du [déploiement de la mise en miroir SQL pour la haute disponibilité du serveur principal dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

