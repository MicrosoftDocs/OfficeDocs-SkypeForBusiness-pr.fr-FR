---
title: Vérifier que tous les objets contact de messagerie unifiée Exchange sont supprimés du pool hérité
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e638dc7e0172c3187859797776f8e64372c81d5
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Vérifier que tous les objets contact de messagerie unifiée Exchange sont supprimés du pool hérité

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

Utilisez l’outil **OCSUmUtil** ou la cmdlet **Get-CsExumContact** pour vérifier que les objets contact de messagerie unifiée Exchange ont été supprimés du pool Office Communications Server 2007 R2 hérité. **OCSUmUtil** se trouve dans le dossier suivant :

% Program Files% \\ fichiers communs de \\ \\ prise en charge de Lync Server 2013 \\OcsUMUtil.exe

**OCSUmUtil** doit être exécuté à partir d’un compte d’utilisateur qui remplit les conditions suivantes :

  - appartenance aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins (ce qui inclut les droits de lecture des paramètres de messagerie unifiée Exchange Server) ;

  - autorisations de domaine pour la création d’objets contact dans le conteneur d’unités d’organisation spécifié.

Pour plus d’informations sur l’utilisation de la cmdlet **Get-CsExumContact** , voir [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) dans la documentation de Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

