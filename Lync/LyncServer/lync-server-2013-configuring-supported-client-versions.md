---
title: 'Lync Server 2013 : configuration des versions clientes prises en charge'
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
ms.openlocfilehash: 9a262cab2145013d83cdae573d98b5db17e0e890
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Configuration des versions clientes prises en charge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-14_

Dans Lync Server 2013, vous pouvez configurer des stratégies de version de client pour spécifier les versions des clients qui sont prises en charge dans votre environnement. De plus, vous pouvez utiliser la configuration de la version du client global pour spécifier une action par défaut pour les clients qui ne disposent pas encore d’une stratégie de version définie et ne sont donc pas explicitement pris en charge ou limités.

Vous pouvez également utiliser des stratégies de version de client pour gérer les mises à jour du client. Lorsque vous définissez une stratégie de version de client et que vous utilisez les options **autoriser et** mettre à niveau et **bloquer et mettre à niveau**, les clients reçoivent le logiciel mis à jour du service Windows Server Update (si vous utilisez ce service) ou de Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Paramètres de la stratégie de version du client

La stratégie de version de client par défaut exige que tous les clients exécutent Lync. Si les clients de votre environnement exécutent des versions antérieures de Communicator, il est possible que vous deviez reconfigurer les règles de version de client pour empêcher le blocage ou la mise à jour inattendue des clients et des appareils lors de la connexion à Lync Server 2013. Vous pouvez modifier la règle par défaut ou ajouter une règle plus haut dans la liste des stratégies de version du client pour remplacer la règle par défaut. Par ailleurs, dans la mesure où les mises à jour cumulatives (CUs) sont disponibles, vous devez configurer la stratégie de version du client pour exiger les mises à jour les plus récentes. Pour plus d’informations, reportez-vous [à la rubrique Spécification des applications clientes qui peuvent être utilisées pour vous connecter à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) dans la documentation sur les opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

