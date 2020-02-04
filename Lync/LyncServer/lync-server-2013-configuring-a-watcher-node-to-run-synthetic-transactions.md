---
title: 'Lync Server 2013 : configuration d’un nœud d’observateur pour exécuter des transactions synthétiques'
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
ms.openlocfilehash: 19211c786c288326d5769824524f5571e5df2f00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Configuration d’un nœud d’observateur pour exécuter des transactions synthétiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Une fois les fichiers de l’agent de centre système installés, vous devez configurer le nœud de l’observateur. Les étapes à suivre pour configurer un nœud d’observateur varient selon que votre ordinateur de nœud de l’observateur se trouve à l’intérieur du réseau de périmètre ou en dehors de votre réseau de périmètre.

Lorsque vous configurez un nœud observateur, vous devez également sélectionner le type de méthode d’authentification utilisé par ce nœud. Lync Server 2013 vous permet de choisir parmi deux méthodes d’authentification : serveur de confiance ou authentification des informations d’identification. Les différences entre ces deux méthodes sont décrites dans le tableau suivant :


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
<td><p>Serveur de confiance</p></td>
<td><p>Utilise un certificat pour emprunter l’identité d’un serveur interne et contourner les demandes d’authentification.</p>
<p>Cette fonctionnalité est utile pour les administrateurs préférant gérer un certificat unique au lieu de nombreux mots de passe d’utilisateur sur chaque nœud d’observateur.</p></td>
<td><p>Dans l’entreprise</p>
<p>Notez que, dans cette méthode, le nœud Watcher doit se trouver dans le même domaine que les pools surveillés. Si le nœud d’observation et les pools surveillés figurent dans des domaines différents, utilisez plutôt l’authentification des informations d’identification.</p></td>
</tr>
<tr class="even">
<td><p>Authentification des informations d’identification</p></td>
<td><p>Stocke les noms d’utilisateur et les mots de passe de manière sécurisée dans le Gestionnaire d’informations d’identification Windows sur chaque nœud observateur.</p>
<p>Ce mode nécessite une plus grande gestion du mot de passe, mais est la seule option disponible pour les nœuds d’observation situés en dehors de l’entreprise. Ces nœuds observateurs ne peuvent pas être traités comme un point de terminaison approuvé pour l’authentification.</p></td>
<td><p>En dehors de l’entreprise</p>
<p>Dans l’entreprise</p></td>
</tr>
</tbody>
</table>


Vous devez également vérifier que votre pare-feu dispose de règles de trafic entrant pour MonitoringHost. exe et PowerShell. exe. Si ces processus sont bloqués par le pare-feu, vos transactions synthétiques échoueront avec l’erreur 504 (délai d’expiration du serveur).

</div>

<span> </span>

</div>

</div>

</div>

