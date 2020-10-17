---
title: 'Phase 10 : mettre hors service le site hérité'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a8a2871659747b68e7a0dec6a945c6f987219a8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533761"
---
# <a name="phase-10-decommission-legacy-site"></a>Phase 10 : mettre hors service le site hérité

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-16_

Les rubriques suivantes fournissent des conseils dans la mise hors service des pools et la désactivation et la suppression des serveurs et des pools d’un déploiement hérité d’Office Communications Server 2007 R2. Certaines des procédures répertoriées dans cette section ne sont pas requises. Lisez les informations de chacune de ces rubriques pour déterminer la procédure de mise hors service à utiliser.

<div>


> [!WARNING]  
> Si vous avez importé des annuaires de conférence pour la Conférence rendez-vous vers Lync Server 2013, il est important de faire passer la propriété de l’annuaire des conférences à Lync Server 2013 avant de commencer à désaffecter vos pools. Si vous mettez hors service un pool sans transmettre la propriété des annuaires des conférences au préalable, la fonctionnalité de conférence rendez-vous ne fonctionnera plus pour toutes les réunions migrées. Vous devez effectuer l’étape de transmission de propriété une fois pour chaque annuaire des conférences compris dans votre pool hérité.



</div>

<div>


> [!IMPORTANT]  
> Pour plus d’informations sur la migration et la mise à niveau des applications Microsoft Unified Communications Managed API (UCMA), avant de mettre hors service votre environnement hérité, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Déplacer les annuaires des conférences](move-conference-directories.md)

  - [Mettre à jour les enregistrements SRV DNS](update-dns-srv-records_1.md)

  - [Mise hors service des serveurs et des pools](decommissioning-servers-and-pools.md)

  - [Supprimer BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

