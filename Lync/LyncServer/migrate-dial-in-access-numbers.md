---
title: Migration des numéros d’accès entrant
TOCTitle: Migration des numéros d’accès entrant
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49891575
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des numéros d’accès entrant

 

_**Dernière rubrique modifiée :** 2012-10-19_

La migration des numéros d’accès entrants de Lync Server 2010 à Lync Server 2013 nécessite l’exécution de l’applet de commande **Move-CsApplicationEndpoint** pour migrer les objets de contact. Durant la période de coexistence de Lync Server 2010 et Lync Server 2013, les numéros d’accès entrants créés dans Lync Server 2013 se comportent de la même manière que les numéros d’accès entrants créés dans Lync Server 2010, comme il est décrit dans cette section.

Les numéros d’accès entrants créés dans Lync Server 2010 mais déplacés vers Lync Server 2013 ou créés dans Lync Server 2013 avant, pendant ou après la migration possèdent les caractéristiques suivantes :

  - ne s’affichent pas sur les invitations de réunion Office Communications Server 2007 R2 et la page de numéros d’accès entrants.

  - s’affichent sur les invitations de réunion Lync Server 2010 et la page de numéros d’accès entrants.

  - s’affichent sur les invitations de réunion Lync Server 2013 et la page de numéros d’accès entrants.

  - ne peuvent pas être vus ou modifiés dans l’outil d’administration Office Communications Server 2007 R2.

  - peuvent être vus et modifiés dans le Panneau de configuration Lync Server 2010 et dans Lync Server 2010 Management Shell.

  - peuvent être vus et modifiés dans le Panneau de configuration Lync Server 2013 et dans Lync Server 2013 Management Shell.

  - peuvent être séquencés à nouveau dans la région à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priorité.

Vous devez finir la migration des numéros d’accès entrants qui pointent vers un pool Lync Server 2010 avant de désactiver ce pool. Si vous ne terminez pas la migration des numéros d’accès entrants telle que décrite dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.

> [!IMPORTANT]  
> Vous devez effectuer cette procédure avant de désactiver le pool Lync Server 2010.

> [!NOTE]  
> Nous vous recommandons d’effectuer le déplacement des numéros d’accès entrants en période de faible utilisation du réseau, au cas où une brève interruption du service surviendrait.

**Pour identifier et déplacer les numéros d’accès entrants**

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, à partir de la ligne de commande exécutée :
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Ouvrez le Panneau de configuration Lync Server.

4.  Dans la barre de navigation de gauche, cliquez sur **Conférences**.

5.  Cliquez sur l’onglet **Numéro d’accès entrant**.

6.  Vérifiez qu’il ne reste aucun numéro d’accès entrant pour le pool Lync Server 2010 à partir duquel vous effectuez la migration.
    
    > [!NOTE]  
    > Lorsque tous les numéros d’accès entrants pointent vers le pool Lync Server 2013, vous pouvez désactiver le pool Lync Server 2010.

**Vérifiez la migration des numéros d’accès entrants à l’aide du Panneau de configuration Lync Server**

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles **CsUserAdministrator** ou **CsAdministrator**, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Conférences**.

4.  Cliquez sur l’onglet **Numéro d’accès entrant**.

5.  Vérifiez que tous les numéros d’accès entrants ont migré vers le pool hébergé sur Lync Server 2013.

**Vérifiez la migration des numéros d’accès entrants à l’aide de Lync Server Management Shell**

1.  Ouvrez le Lync Server Management Shell.

2.  Pour renvoyer tous les numéros d’accès de conférence entrants migrés, à partir de la ligne de commande exécutée :
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Vérifiez que tous les numéros d’accès entrants ont migré vers le pool hébergé sur Lync Server 2013.

