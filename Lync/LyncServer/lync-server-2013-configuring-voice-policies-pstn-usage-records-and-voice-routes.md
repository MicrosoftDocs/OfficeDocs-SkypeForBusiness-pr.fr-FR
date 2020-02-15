---
title: Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fc69514b425c6a619a0edcd349a8b8733eca369
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a>Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Les stratégies de voix, les enregistrements d’utilisation PSTN et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter des enregistrements d’utilisation PSTN à la stratégie, qui spécifient les droits qui sont accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation PSTN, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs peuvent uniquement effectuer des appels qui utilisent des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation PSTN correspondants.

La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer à configurer une stratégie de voix qui comprend les enregistrements d’utilisation PSTN appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation PSTN.

<div>


> [!NOTE]
> Vous pouvez également créer des stratégies de voix avec l’étendue d’<EM>utilisateur</EM> et les affecter à des utilisateurs ou des groupes individuels.



</div>

Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, voir les procédures dans cette section.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Afficher les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)

  - [Configuration des itinéraires des communications vocales pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Exportation et importation de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

