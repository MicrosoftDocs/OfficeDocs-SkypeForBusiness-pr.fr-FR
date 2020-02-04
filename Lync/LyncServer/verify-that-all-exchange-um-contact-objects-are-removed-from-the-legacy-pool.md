---
title: Vérifier que tous les objets de contact Exchange UM sont supprimés du pool hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e49aa2fdef3731a34de05e04b8195cb8aa32cd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Vérifier que tous les objets de contact Exchange UM sont supprimés du pool hérité

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

Utilisez l’outil **OCSUmUtil** ou l’applet de contrôle **Get-CsExumContact** pour vérifier que les objets de contact de messagerie unifiée Exchange ont été supprimés du pool Office Communications Server 2007 R2 hérité. **OCSUmUtil** se trouve dans le dossier suivant :

% Program Files%\\Common Files\\Lync Server 2013\\support\\OcsUMUtil. exe

**OCSUmUtil** doit être exécuté à partir d’un compte d’utilisateur disposant des éléments suivants :

  - Appartenance au groupe RTCUniversalServerAdmins et RTCUniversalUserAdmins (y compris les droits pour lire les paramètres de messagerie unifiée Exchange Server)

  - Droits de domaine pour créer des objets de contact dans le conteneur d’unité d’organisation (UO) spécifié

Pour plus d’informations sur l’utilisation de l’applet de connexion **Get-CsExumContact** , voir [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) dans la documentation Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

