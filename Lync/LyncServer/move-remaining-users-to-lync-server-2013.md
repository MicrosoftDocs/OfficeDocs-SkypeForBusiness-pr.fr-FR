---
title: Déplacer les utilisateurs restants vers Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43be496d0fea280374358b1967ee899ad67624b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Déplacer les utilisateurs restants vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

Vous pouvez déplacer des utilisateurs vers le nouveau déploiement Lync Server 2013 à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell. Vous devez respecter certaines exigences pour garantir une transition sans complication vers Lync Server 2013. Pour plus d’informations sur les conditions préalables à la réalisation des procédures de cette rubrique, voir [configure clients for Migration](configure-clients-for-migration.md). Pour obtenir la procédure détaillée sur le déplacement des utilisateurs, reportez-vous [à la section phase 4 : déplacer les utilisateurs test vers le pool pilote](phase-4-move-test-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory ou les outils d’administration Lync Server 2010 pour déplacer des utilisateurs de votre environnement hérité vers Lync Server 2013.



</div>

Lorsque vous déplacez un utilisateur vers un pool Lync Server 2013, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool.

<div>


> [!IMPORTANT]  
> Cela comprend des réunions actives créées par l’utilisateur hérité. Par exemple, si un utilisateur hérité a configuré une conférence <STRONG>mon réunion</STRONG> , cette conférence sera toujours disponible dans le nouveau pool Lync Server 2013 une fois que l’utilisateur a été déplacé. Les détails permettant d’accéder à cette réunion seront encore les mêmes <STRONG>URL de conférence et ID de conférence</STRONG>. La seule différence réside dans le fait que la Conférence est désormais hébergée dans le pool Lync Server 2013, et non dans le pool Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Le fait d’héberger des utilisateurs sur Lync Server 2013 n’exige pas que vous déployiez des clients mis à niveau en même temps. Les nouvelles fonctionnalités sont disponibles pour les utilisateurs uniquement lorsqu’ils ont effectué la mise à niveau vers le nouveau logiciel client.



</div>

<div>

## <a name="post-migration-task"></a>Tâche post-migration

1.  Une fois que vous avez déplacé des utilisateurs, vérifiez la stratégie de conférence qui leur est attribuée.

2.  Pour vous assurer que les réunions organisées par les utilisateurs hébergés sur Lync Server 2013 fonctionnent de manière transparente avec les utilisateurs fédérés qui sont hébergés sur Lync Server 2010, la stratégie de conférence affectée aux utilisateurs migrés doit autoriser les participants anonymes.

3.  Les stratégies de conférence qui permettent aux participants anonymes ont **autorisé les participants à inviter des utilisateurs anonymes** sélectionnés dans le panneau de configuration lync Server 2013 et ont **Allowanonymousparticipantsinmeetings ayant** défini sur **true** dans la sortie de l’applet de commande **Get-CsConferencingPolicy** dans Lync Server Management Shell.

4.  Pour plus d’informations sur la configuration de la stratégie de conférence à l’aide de Lync Server Management Shell, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) dans la documentation de Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

