---
title: Faire migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 383fed15e2b67013ddd85356eb141a4c5dcf64e6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Faire migrer les numéros d’accès entrant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

La migration des numéros d’accès entrant de Lync Server 2010 vers Lync Server 2013 nécessite l’exécution de la cmdlet **Move-CsApplicationEndpoint** pour migrer les objets contact. Pendant la période de coexistence Lync Server 2010 et Lync Server 2013, les numéros d’accès entrant que vous avez créés dans Lync Server 2013 se comportent de la même manière que les numéros d’accès entrant que vous créez dans Lync Server 2010, comme décrit dans cette section.

Les numéros d’accès entrant que vous avez créés dans Lync Server 2010, mais déplacés vers Lync Server 2013 ou créés dans Lync Server 2013 avant, pendant ou après la migration, ont les caractéristiques suivantes :

  - N’apparaissent pas sur les invitations aux réunions Office Communications Server 2007 R2 et la page numéro d’accès entrant.

  - Apparaissent sur les invitations aux réunions Lync Server 2010 et la page numéro d’accès entrant.

  - Apparaissent sur les invitations aux réunions Lync Server 2013 et la page numéro d’accès entrant.

  - Ne peuvent pas être affichés ni modifiés dans l’outil d’administration Office Communications Server 2007 R2.

  - Peuvent être affichés et modifiés dans le panneau de configuration Lync Server 2010 et dans Lync Server 2010 Management Shell.

  - Peuvent être affichés et modifiés dans le panneau de configuration Lync Server 2013 et dans Lync Server 2013 Management Shell.

  - ils peuvent être réordonnés dans la région à l’aide de l’applet de commande Set-CsDialinConferencingAccessNumber avec le paramètre Priority.

Vous devez terminer la migration des numéros d’accès entrant qui pointent vers un pool Lync Server 2010 avant de mettre hors service le pool Lync Server 2010. Si vous ne terminez pas la migration des numéros d’accès entrant tel que décrit dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.

<div>


> [!IMPORTANT]  
> Vous devez effectuer cette procédure avant de désactiver le pool Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Nous vous recommandons de déplacer les numéros d’accès entrant lorsque l’utilisation du réseau est faible, au cas où il y aurait une courte période d’interruption de service.



</div>

**Pour identifier et déplacer les numéros d’accès entrant**

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, exécutez la commande suivante à partir de la ligne de commande :
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Ouvrez le Panneau de configuration Lync Server.

4.  Dans la barre de navigation de gauche, cliquez sur **Conférence**.

5.  Cliquez sur l’onglet **numéro d’accès entrant** .

6.  Vérifiez qu’il ne reste aucun numéro d’accès entrant pour le pool Lync Server 2010 à partir duquel vous effectuez la migration.
    
    <div>
    

    > [!NOTE]  
    > Lorsque tous les numéros d’accès entrants pointent vers le pool Lync Server 2013, vous pouvez mettre hors service le pool Lync Server 2010.

    
    </div>

**Vérifier la migration des numéros d’accès entrant à l’aide du panneau de configuration Lync Server**

1.  À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou **CsAdministrator** , ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**.

4.  Cliquez sur l’onglet **numéro d’accès entrant** .

5.  Vérifiez que tous les numéros d’accès entrant sont migrés vers le pool hébergé sur Lync Server 2013.

**Vérifier la migration des numéros d’accès entrant à l’aide de Lync Server Management Shell**

1.  Ouvrez Lync Server Management Shell.

2.  Pour renvoyer tous les numéros d’accès de conférence rendez-vous migrés, exécutez la commande suivante à partir de la ligne de commande :
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Vérifiez que tous les numéros d’accès entrant sont migrés vers le pool hébergé sur Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

