---
title: 'Lync Server 2013 : configuration de la base de données d’emplacements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f79587526172c7ccade1b74574b20657d1a82300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configuration de la base de données d’emplacements dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements. Si vous ne configurez pas de base de données d’emplacements et que l’option **Emplacement obligatoire** est définie sur **Oui** ou **Clause d’exclusion de responsabilité** dans la stratégie d’emplacement, l’utilisateur sera invité à entrer manuellement un emplacement.

Pour configurer la base de données d’emplacements, vous devrez effectuer les tâches suivantes :

1.  Remplir la base de données avec une correspondance des éléments réseau avec les emplacements. Si vous utilisez une passerelle ELIN (Emergency location Identification Number), vous devez inclure le ELIN dans le \<champ\> CompanyName.

2.  Valider les adresses par rapport à la base de données MSAG gérée par le fournisseur de service E9-1-1.

3.  Publier la base de données mise à jour.

<div>


> [!NOTE]  
> Vous pouvez également définir une base de données d’emplacements source secondaire pouvant être utilisée à la place de la base de données d’emplacements. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configure-a-secondary-location-information-service.md">la rubrique Configure a Secondary location information service in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Remplir la base de données d’emplacements dans Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Valider des adresses dans Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Publier la base de données d’emplacements à partir de Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

