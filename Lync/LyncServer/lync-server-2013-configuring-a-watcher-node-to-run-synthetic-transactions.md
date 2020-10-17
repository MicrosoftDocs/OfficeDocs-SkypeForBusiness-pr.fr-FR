---
title: 'Lync Server 2013 : configuration d’un nœud observateur pour exécuter des transactions synthétiques'
description: 'Lync Server 2013 : configuration d’un nœud observateur pour exécuter des transactions synthétiques.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5fdb3d1a1499a6ef79e962a41d9eb3ee174c33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567880"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Configuration d’un nœud observateur pour exécuter des transactions synthétiques dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Une fois les fichiers de l’agent System Center installés, vous devez configurer le nœud observateur. La procédure varie selon que l’ordinateur du nœud observateur se trouve à l’intérieur ou à l’extérieur de votre réseau de périphérie.

Lorsque vous configurez un nœud observateur, vous devez également choisir le type de méthode d’authentification utilisé par ce nœud. Lync Server 2013 vous permet de choisir l’une des deux méthodes d’authentification suivantes : serveur approuvé ou authentification des informations d’identification. Les différences entre ces deux méthodes sont indiquées dans le tableau suivant :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuration</th>
<th>Description</th>
<th>Emplacements pris en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur approuvé</p></td>
<td><p>Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.</p>
<p>Utile pour les administrateurs qui préfèrent gérer un seul certificat au lieu de plusieurs mots de passe d’utilisateur sur chaque nœud observateur.</p></td>
<td><p>Au sein de l’entreprise.</p>
<p>Notez qu’avec cette méthode, le nœud observateur doit se trouver dans le même domaine que les pools surveillés. Si le nœud observateur et les pools surveillés se trouvent dans des domaines différents, utilisez l’authentification des informations d’identification à la place.</p></td>
</tr>
<tr class="even">
<td><p>Authentification des informations d’identification</p></td>
<td><p>Stocke les noms d’utilisateur et mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.</p>
<p>Ce mode implique davantage d’opérations de gestion des mots de passe, mais est la seule option pour les nœuds observateurs situés en dehors de l’entreprise. Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.</p></td>
<td><p>En dehors de l’entreprise.</p>
<p>Au sein de l’entreprise.</p></td>
</tr>
</tbody>
</table>


Vous devez également vérifier que votre pare-feu comporte des règles de trafic entrant pour MonitoringHost.exe et PowerShell.exe. Si ces processus sont bloqués par le pare-feu, vos transactions synthétiques échouent avec une erreur 504 (délai d’attente du serveur).

</div>

<span> </span>

</div>

</div>

</div>

