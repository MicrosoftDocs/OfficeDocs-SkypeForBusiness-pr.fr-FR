---
title: Migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0638ae76a9aa1108b11c1d1ff98fdd3eef08c938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrer les numéros d’accès entrant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

La migration des numéros d’accès rendez-vous de Lync Server 2010 vers Lync Server 2013 nécessite l’exécution de l’applet de connexion **Move-CsApplicationEndpoint** pour migrer les objets de contact. Pendant la période de coexistence Lync Server 2010 et Lync Server 2013, les numéros d’accès rendez-vous créés dans Lync Server 2013 se comportent de la même manière que les numéros d’accès rendez-vous créés dans Lync Server 2010, comme décrit dans cette section.

Les numéros d’accès rendez-vous que vous avez créés dans Lync Server 2010, mais qui ont été déplacés vers Lync Server 2013 ou que vous avez créés dans Lync Server 2013 auparavant, pendant ou après la migration, présentent les caractéristiques suivantes :

  - N’apparaissent pas dans les invitations aux réunions Office Communications Server 2007 R2 et la page numéro d’accès rendez-vous.

  - S’affichent dans les invitations aux réunions Lync Server 2010 et la page numéro d’accès rendez-vous.

  - S’affichent dans les invitations aux réunions Lync Server 2013 et la page numéro d’accès rendez-vous.

  - Ne peut pas être affiché ou modifié dans l’outil d’administration d’Office Communications Server 2007 R2.

  - Peut être affiché et modifié dans le panneau de configuration de Lync Server 2010 et dans Lync Server 2010 Management Shell.

  - Peut être affiché et modifié dans le panneau de configuration de Lync Server 2013 et dans Lync Server 2013 Management Shell.

  - Peuvent être réécrits au sein de la région à l’aide de l’applet de requête Set-CsDialinConferencingAccessNumber avec le paramètre Priority.

Vous devez terminer la migration des numéros d’accès rendez-vous qui pointent vers un pool Lync Server 2010 avant de désactiver le pool Lync Server 2010. Si vous n’avez pas terminé la migration des numéros d’accès rendez-vous, comme indiqué dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.

<div>


> [!IMPORTANT]  
> Vous devez effectuer cette procédure avant de désaffecter le pool Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Nous vous recommandons de déplacer les numéros d’accès rendez-vous lorsque le niveau d’utilisation du réseau est faible, en cas de panne de service de courte durée.



</div>

**Pour identifier et déplacer les numéros d’accès rendez-vous**

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, à partir de la ligne de commande :
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Ouvrez le Paneau de configuration Lync Server.

4.  Dans la barre de navigation de gauche, cliquez sur **Conférences**.

5.  Cliquez sur l’onglet **numéro d’accès** rendez-vous.

6.  Vérifiez qu’aucun numéro d’accès par connexion n’est conservé pour le pool Lync Server 2010 à partir duquel vous effectuez la migration.
    
    <div>
    

    > [!NOTE]  
    > Lorsque tous les numéros d’accès par connexion pointent vers le pool Lync Server 2013, vous pouvez désactiver le pool Lync Server 2010.

    
    </div>

**Vérifier la migration des numéros d’accès rendez-vous à l’aide du panneau de configuration de Lync Server**

1.  À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou au rôle **CsAdministrator** , connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez le Paneau de configuration Lync Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Conférences**.

4.  Cliquez sur l’onglet **numéro d’accès** rendez-vous.

5.  Vérifiez que tous les numéros d’accès rendez-vous sont déplacés vers le pool hébergé sur Lync Server 2013.

**Vérifier la migration des numéros d’accès entrants à l’aide de Lync Server Management Shell**

1.  Ouvrez Lync Server Management Shell.

2.  Pour rétablir tous les numéros d’accès pour les conférences rendez-vous transférés, à partir de la ligne de commande :
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Vérifiez que tous les numéros d’accès rendez-vous sont déplacés vers le pool hébergé sur Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

