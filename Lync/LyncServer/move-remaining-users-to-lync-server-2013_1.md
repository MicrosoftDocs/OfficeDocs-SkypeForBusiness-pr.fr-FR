---
title: Déplacement des autres utilisateurs vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb5a709e896b66a1c8cd33a930bfeed5e05644f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Déplacement des autres utilisateurs vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

Vous pouvez déplacer des utilisateurs vers le nouveau déploiement de Lync Server 2013 à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell. Vous devez respecter certaines exigences pour garantir une transition fluide vers Lync Server 2013. Pour plus d’informations sur les conditions préalables à l’exécution des procédures décrites dans cette rubrique, voir [configurer des clients pour la migration](configure-clients-for-migration_1.md). Pour plus d’informations sur le déplacement des utilisateurs, voir [phase 6 : déplacer des utilisateurs vers le pool de pilotes](phase-6-move-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory ou les outils d’administration de Microsoft Office Communications Server 2007 R2 pour déplacer des utilisateurs de votre environnement hérité vers Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> L’applet de <STRONG>passe Move-CsLegacyUser</STRONG> nécessite que les noms d’utilisateur soient correctement formés et qu’ils n’utilisent pas d’espaces de début ou de fin. Vous ne pouvez pas déplacer un compte d’utilisateur à l’aide de l’applet de l’applet de <STRONG>déplacement-CsLegacyUser</STRONG> si celle-ci contient des espaces de début ou de fin.



</div>

Lorsque vous déplacez un utilisateur vers un pool Lync Server 2013, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool.

<div>


> [!IMPORTANT]  
> Cela inclut les réunions actives créées par l’ancien utilisateur. Par exemple, si un utilisateur hérité a configuré une conférence <STRONG>ma réunion</STRONG> , cette conférence sera toujours disponible dans le nouveau pool Lync Server 2013, une fois que l’utilisateur a été déplacé. Les détails permettant d’accéder à cette réunion seront toujours les mêmes <STRONG>URL et ID de conférence</STRONG>. La seule différence réside dans le fait que la Conférence est désormais hébergée dans le pool Lync Server 2013, et non dans le pool Office Communications Server 2007 R2.



</div>

<div>


> [!NOTE]  
> L’hébergement d’utilisateurs sur Lync Server 2013 ne nécessite pas le déploiement simultané de clients mis à niveau. Les nouvelles fonctionnalités ne seront accessibles qu’aux utilisateurs qui ont procédé à la mise à niveau vers le nouveau logiciel client.



</div>

<div>

## <a name="post-migration-task"></a>Tâche après migration

1.  Après le déplacement des utilisateurs, vérifiez la stratégie de conférence qui leur est affectée.

2.  Pour vous assurer que les réunions organisées par les utilisateurs hébergés sur Lync Server 2013 fonctionnent en toute transparence avec les utilisateurs fédérés qui sont hébergés sur Office Communications Server 2007 R2, la stratégie de conférence affectée aux utilisateurs migrés doit permettre aux participants anonymes.

3.  Les stratégies de conférence autorisant les participants anonymes ont la **possibilité d’inviter les utilisateurs anonymes** sélectionnés dans lync Server 2013 panneau de configuration et de définir **AllowAnonymousParticipantsInMeetings** sur **true** dans la sortie de l’applet de commande **Get-CsConferencingPolicy** dans Lync Server Management Shell.

4.  Pour plus d’informations sur la configuration d’une stratégie de conférence à l’aide de Lync Server Management Shell, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) dans la documentation Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

