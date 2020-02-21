---
title: 'Lync Server 2013 : configuration des versions du client prises en charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Configuration des versions de client prises en charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-14_

Dans Lync Server 2013, vous pouvez configurer des stratégies de version du client pour spécifier les versions des clients prises en charge dans votre environnement. En outre, vous pouvez utiliser la configuration de version du client globale pour spécifier une action par défaut pour les clients qui n’ont pas encore de stratégie de version définie et, par conséquent, ne sont pas explicitement prises en charge ou restreintes.

Vous pouvez également utiliser des stratégies de version du client pour gérer les mises à jour du client. Lorsque vous définissez une stratégie de version de client et utilisez les options **autoriser et mettre à niveau** et **bloquer et mettre à niveau**, les clients recevront des logiciels mis à jour à partir du service de mise à jour de Windows Server (si vous utilisez ce service) ou à partir de Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Paramètres de la stratégie de version de client

La stratégie de version de client par défaut exige que tous les clients exécutent Lync. Si les clients de votre environnement exécutent des versions antérieures de Communicator, il se peut que vous deviez reconfigurer les règles de version du client pour empêcher les clients et les appareils d’être bloqués ou mis à jour de manière inattendue lors de la connexion à Lync Server 2013. Vous pouvez modifier la règle par défaut ou la remplacer en ajoutant une règle supérieure dans la liste des stratégies de version de client. De plus, à mesure que des mises à jour cumulatives sont publiées, vous devez configurer la stratégie de version de client pour demander les dernières mises à jour. Pour plus d’informations, reportez-vous à la rubrique [spécification des applications clientes pouvant être utilisées pour se connecter à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) dans la documentation des opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

