---
title: 'Lync Server 2013 : créer des groupes d’agents Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b4f97ad93ecdbfef9e8e170c999f8c9860f830
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>Créer des groupes d’agents Response Group Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

Lorsque vous créez un groupe d’agents, vous sélectionnez les agents assignés au groupe et spécifiez divers autres paramètres du groupe. Vous pouvez ainsi sélectionner la méthode de routage des appels et spécifier si un agent peut se connecter au groupe et s’en déconnecter.

Un agent qui doit se connecter et se déconnecter du groupe, qui est différent de la connexion ou de la sortie de Lync Server, est appelé *agent formel*. Les agents formels doivent être connectés au groupe pour recevoir des appels acheminés vers le groupe. Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe. Les agents formels se connectent et se déconnectent de leurs groupes en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Internet Windows Internet Explorer et afficher une console de page Web.

Un agent qui ne se connecte pas ou n’est pas en dehors du groupe est appelé *agent informel*. Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server, et ils ne peuvent pas se déconnecter du groupe.

<div>


> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de local vers en ligne, les appels Response Group ne sont pas acheminés vers cet agent.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

[Création ou modification d’un groupe d’agents dans Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

