---
title: 'Étape 10: désaffecter le site hérité'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04054c158f1c97f5090328e1277dcdb63b1d823
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>Étape 10: désaffecter le site hérité

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-16_

Les rubriques suivantes fournissent des recommandations en matière de mise en service de pools, et de désactivation et de suppression de serveurs et de pools à partir d’un déploiement hérité d’Office Communications Server 2007 R2. Toutes les procédures indiquées dans cette section ne sont pas obligatoires. Lisez les informations contenues dans ces rubriques pour déterminer la procédure de désactivation à utiliser.

<div>


> [!WARNING]  
> Si vous avez importé des annuaires de conférences pour les conférences rendez-vous sur Lync Server 2013, il est important de basculer la propriété de l’annuaire de conférences vers Lync Server 2013 avant de commencer à mettre vos pools en service. Si vous désorganisez un pool sans avoir préalablement transféré la propriété de l’annuaire de conférences, la fonctionnalité de connexion à toutes les réunions migrées ne fonctionnera plus. Vous devez effectuer cette étape pour une transition de propriété unique pour chaque annuaire de conférences de votre pool hérité.



</div>

<div>


> [!IMPORTANT]  
> Pour plus d’informations sur la migration et la mise à niveau des applications UCMA (Unified Communications Managed API), avant de désaffecter votre environnement hérité, voir<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Déplacer des répertoires de conférences](move-conference-directories.md)

  - [Mettre à jour les enregistrements SRV DNS](update-dns-srv-records_1.md)

  - [Désaffectation de serveurs et de pools](decommissioning-servers-and-pools.md)

  - [Supprimer BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

