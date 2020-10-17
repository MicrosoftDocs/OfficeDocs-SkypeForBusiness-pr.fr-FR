---
title: 'Lync Server 2013 : gestion des groupes d’agents Response Group'
description: 'Lync Server 2013 : gestion des groupes d’agents Response Group.'
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
ms.openlocfilehash: 23a4f430981689f9794c05aa1472ff61cd32cd5f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569390"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Gestion des groupes d’agents Response Group dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Un groupe d’agents se compose d’un groupe de personnes désigné pour répondre aux appels à un groupe Response Group. Lorsque vous créez un groupe d’agents, vous sélectionnez les agents qui sont affectés au groupe et spécifiez des paramètres de groupe supplémentaires, tels que la méthode de routage et si un agent peut se connecter au groupe et s’en déconnecter.

<div>


> [!NOTE]  
> Les utilisateurs doivent être activés pour voix entreprise avant de pouvoir les ajouter à des groupes d’agents. Pour plus d’informations sur l’activation d’un utilisateur pour voix entreprise, reportez-vous à la rubrique <A href="lync-server-2013-enable-users-for-enterprise-voice.md">activation des utilisateurs pour voix entreprise dans Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de local vers en ligne, les appels Response Group ne sont pas acheminés vers cet agent.



</div>

Un agent qui doit se connecter et se déconnecter du groupe, qui est différent de la connexion ou de la sortie de Lync Server, est appelé *agent formel*. Les agents formels doivent être connectés au groupe pour pouvoir recevoir des appels routés vers le groupe. Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe. Les agents formels se connectent et se déconnectent de leurs groupes en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Internet Windows Internet Explorer et afficher une console de page Web.

Un agent qui ne se connecte pas ou n’est pas en dehors du groupe est appelé *agent informel*. Les agents informels sont automatiquement connectés au groupe lorsqu’ils se connectent à Lync Server, et ils ne peuvent pas se déconnecter du groupe.

<div>


> [!IMPORTANT]  
> Lorsque vous affectez des utilisateurs en tant qu’agents au groupe de réponses, informez-les que, s’ils ont activé le mode de confidentialité, ils doivent rechercher des contacts « RGS Presence Watcher » et les ajouter à leur liste de contacts. Les agents dont le mode de confidentialité est activé, mais qui n’ont pas « RGS presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels vers le groupe Response Group. Cela ne concerne pas les agents qui n’ont pas activé le mode de confidentialité.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Création ou modification d’un groupe d’agents dans Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Supprimer un groupe d’agents dans Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

