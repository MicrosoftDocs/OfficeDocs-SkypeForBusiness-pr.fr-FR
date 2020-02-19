---
title: 'Lync Server 2013 : exporter un fichier de configuration d’itinéraire des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9cc4eb13c8605d20d87d851009e066c48439fe8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>Exporter un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Si vous souhaitez enregistrer votre configuration de routage des communications vocales sans la publier, procédez comme suit pour utiliser les commandes exportation et importation de la configuration du panneau de configuration de Lync Server pour enregistrer et récupérer une capture instantanée de la configuration de votre routage des communications vocales. Lorsque vous importez un fichier de configuration de routage des communications vocales (. VCFG), mais que des modifications ont été apportées à la configuration du routage des communications vocales sur le serveur en attendant, les pages du groupe de **routage** des communications vocales dans le panneau de configuration Lync Server indiquent des modifications non validées dans le routage des communications vocales. Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.

Si vous avez apporté des modifications non validées aux paramètres sur une page du groupe, les modifications sont enregistrées dans le fichier de configuration de la voix exporté (. VCFG). Cela vous permet de modifier la configuration du routage des communications vocales lors de sessions multiples avant de publier les modifications.

<div>

## <a name="to-export-a-voice-routing-configuration"></a>Pour exporter une configuration du routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Dans le menu **Actions**, cliquez sur **Exporter la configuration**.

5.  Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Importer un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

