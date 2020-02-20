---
title: Déplacer les utilisateurs restants vers Lync Server 2013
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
ms.openlocfilehash: 40f9dace4a169d58705c88572e0596b04eeb2a9a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Déplacer les utilisateurs restants vers Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

Vous pouvez déplacer des utilisateurs vers le nouveau déploiement Lync Server 2013 à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell. Vous devez respecter certaines exigences pour garantir une transition sans complication vers Lync Server 2013. Pour plus d’informations sur les conditions préalables à la réalisation des procédures de cette rubrique, voir [configure clients for Migration](configure-clients-for-migration_1.md). Pour obtenir la procédure détaillée sur le déplacement des utilisateurs, voir [phase 6 : déplacer des utilisateurs vers le pool pilote](phase-6-move-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le composant logiciel enfichable utilisateurs et ordinateurs Active Directory ou les outils d’administration de Microsoft Office Communications Server 2007 R2 pour déplacer les utilisateurs de votre environnement hérité vers Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> L’applet de commande <STRONG>Move-CsLegacyUser</STRONG> nécessite que les noms d’utilisateurs soient correctement formés, sans espaces de début ou de fin. Vous ne pouvez pas déplacer un compte d’utilisateur à l’aide de l’applet de commande <STRONG>Move-CsLegacyUser</STRONG> s’il contient des espaces de début ou de fin.



</div>

Lorsque vous déplacez un utilisateur vers un pool Lync Server 2013, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool.

<div>


> [!IMPORTANT]  
> Cela comprend des réunions actives créées par l’utilisateur hérité. Par exemple, si un utilisateur hérité a configuré une conférence <STRONG>mon réunion</STRONG> , cette conférence sera toujours disponible dans le nouveau pool Lync Server 2013, après que l’utilisateur a été déplacé. Les détails permettant d’accéder à cette réunion seront encore les mêmes <STRONG>URL de conférence et ID de conférence</STRONG>. La seule différence réside dans le fait que la Conférence est désormais hébergée dans le pool Lync Server 2013, et non dans le pool Office Communications Server 2007 R2.



</div>

<div>


> [!NOTE]  
> Le fait d’héberger des utilisateurs sur Lync Server 2013 n’exige pas que vous déployiez des clients mis à niveau en même temps. Les nouvelles fonctionnalités sont disponibles pour les utilisateurs uniquement lorsqu’ils ont effectué la mise à niveau vers le nouveau logiciel client.



</div>

<div>

## <a name="post-migration-task"></a>Tâche post-migration

1.  Une fois que vous avez déplacé des utilisateurs, vérifiez la stratégie de conférence qui leur est attribuée.

2.  Pour vous assurer que les réunions organisées par les utilisateurs hébergés sur Lync Server 2013 fonctionnent de manière transparente avec les utilisateurs fédérés hébergés sur Office Communications Server 2007 R2, la stratégie de conférence affectée aux utilisateurs migrés doit autoriser les participants anonymes.

3.  Les stratégies de conférence qui permettent aux participants anonymes ont **autorisé les participants à inviter des utilisateurs anonymes** sélectionnés dans le panneau de configuration lync Server 2013 et ont **Allowanonymousparticipantsinmeetings ayant** défini sur **true** dans la sortie de l’applet de commande **Get-CsConferencingPolicy** dans Lync Server Management Shell.

4.  Pour plus d’informations sur la configuration de la stratégie de conférence à l’aide de Lync Server Management Shell, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) dans la documentation de Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

