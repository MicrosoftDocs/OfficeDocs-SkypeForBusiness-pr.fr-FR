---
title: 'Lync Server 2013 : Préparation de la forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Préparation de la forêt pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

La préparation de la forêt crée des paramètres globaux et des objets et des groupes universels Active Directory pour une utilisation par Lync Server 2013 et accorde des autorisations d’accès appropriées aux objets Active Directory. Pour obtenir une description des groupes universels et des paramètres globaux et des objets créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

La préparation de la forêt crée également des objets qui contiennent des jeux de propriétés et des spécificateurs d’affichage qui sont utilisés par Lync Server 2013 et les stocke dans le conteneur de configuration.

<div>


> [!IMPORTANT]  
> Assurez-vous que les modifications de préparation du schéma sont répliquées sur tous les contrôleurs de domaine avant d’effectuer la procédure de préparation de la forêt. Si la réplication n’est pas effectuée, une erreur se produit.



</div>

Si vous effectuez un nouveau déploiement de Lync Server, vous devez stocker les paramètres globaux dans le conteneur de configuration. Si vous effectuez une mise à niveau à partir d’une version antérieure et que vous stockez les paramètres globaux dans le conteneur système, vous pouvez continuer à utiliser le conteneur système.

Pour effectuer cette procédure, vous devez être membre du groupe administrateurs d’entreprise ou admins de domaine pour le domaine racine de la forêt.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Exécution de la préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Utilisation des commandes d’applet pour inverser la préparation d’une forêt pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

