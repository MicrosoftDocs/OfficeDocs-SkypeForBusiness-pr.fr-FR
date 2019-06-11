---
title: Vérification de la connectivité entre les serveurs internes et les serveurs Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3868462036312be97484e41c69b51ae022b57c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>Vérification de la connectivité entre les serveurs internes et les serveurs Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

Dans Lync Server 2013, un Assistant validation distinct a été disponible pour vous permettre de valider la connectivité entre les serveurs Edge et les serveurs internes. Dans Lync Server 2013, la validation de la connectivité est exécutée automatiquement lorsque vous installez vos serveurs Edge.

Vous pouvez valider la réplication des informations de configuration sur le bord en exécutant l’applet de contrôle Windows PowerShell **Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve la Banque centrale de gestion (ou n’importe quel domaine joint. ordinateur sur lequel sont installés les composants principaux de Lync Server 2013 (OcsCore. msi). Les résultats initiaux risquent d’indiquer l’état «false» au lieu de «true» pour la réplication. Si tel est le cas, exécutez l’applet de connexion **Invoke-CsManagementStoreReplication** et attendez la fin de la réplication avant d’exécuter de nouveau **Get-CsManagementStoreReplicationStatus** .

Vous pouvez vérifier la connectivité des utilisateurs externes séparément, y compris à l’aide de l’analyseur de connectivité à distance d’Office Communications Server pour vérifier la connectivité des utilisateurs distants. Pour plus d’informations, consultez [Vérifier la connectivité des utilisateurs externes dans Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).

</div>

<span> </span>

</div>

</div>

</div>

