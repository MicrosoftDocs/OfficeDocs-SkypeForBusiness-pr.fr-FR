---
title: 'Lync Server 2013 : gestion des groupes d’agents de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Gestion des groupes d’agents de Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Un groupe d’agents se compose d’un groupe de personnes qui sont conçues pour répondre aux appels d’un Response Group. Lorsque vous créez un groupe d’agents, vous sélectionnez les agents qui sont affectés au groupe et spécifiez des paramètres de groupe supplémentaires, tels que la méthode de routage, et la possibilité pour un agent de se connecter au groupe et de s’en déconnecter.

<div>


> [!NOTE]  
> Les utilisateurs doivent être activés pour voix entreprise avant de pouvoir les ajouter aux groupes d’agents. Pour plus d’informations sur l’activation d’un utilisateur pour la voix entreprise, voir <A href="lync-server-2013-enable-users-for-enterprise-voice.md">activer les utilisateurs d’Enterprise Voice dans Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de local vers en ligne, les appels de groupe de réponse ne seront pas routés vers cet agent.



</div>

Un agent qui doit se connecter ou se déconnecter du groupe, qui est différent de la connexion ou de la déconnexion de Lync Server, est appelé *agent formel*. Les agents officiels doivent être connectés au groupe pour pouvoir recevoir des appels routés vers le groupe. Cela peut s’avérer utile pour les agents qui répondent à temps partiel aux appels du groupe. Les agents officiels se connectent à leurs groupes en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Internet de Windows Internet Explorer et afficher une console Web.

Un agent qui ne se connecte pas ou n’utilise pas le groupe est appelé *agent informel*. Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server et ne peuvent pas se déconnecter du groupe.

<div>


> [!IMPORTANT]  
> Lorsque vous affectez des utilisateurs comme agents de groupe de réponse, informez-les que, si leur mode de confidentialité est activé, ils doivent rechercher des contacts « RGS Presence Watcher » et les rajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont aucun contact « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe de réponse. Les agents dont le mode de confidentialité n’est pas activé ne seront pas affectés.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Créer ou modifier un groupe d’agents dans Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Supprimer un groupe d’agents dans Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

