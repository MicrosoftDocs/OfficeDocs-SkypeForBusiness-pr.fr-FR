---
title: Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement
description: Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74e4a399e8010cfc22430216ef6e3c11fc9a7bdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567550"
---
# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Si un client se trouve en dehors du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement. Toutefois, pendant un appel d’urgence, l’appel est d’abord acheminé vers un centre de réponse aux appels d’urgence (ECRC) national/régional E9-1-1, avant d’être acheminé vers un point de contrôle de la sécurité publique (PSAPI). L’ECRC interroge oralement l’appelant pour un emplacement, puis transfère l’appel vers le PSAPI approprié, en fonction des informations fournies.

  - **Les utilisateurs doivent-ils être invités à entrer un emplacement lorsque l’utilisateur n’est pas fourni automatiquement par le service d’informations d’emplacement ?**  
    Par exemple, si un client se trouve dans un sous-réseau non défini, à la maison, dans un hôtel ou ailleurs en dehors du réseau, l’utilisateur doit-il être invité à entrer un emplacement ?
    
    Vous pouvez configurer le paramètre **emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. La définition de cette valeur sur no signifie que l’utilisateur ne sera pas invité à entrer un emplacement. La définition de cette valeur sur Yes signifie que l’utilisateur sera invité à entrer un emplacement, mais peut ignorer l’invite. La définition de cette valeur sur clause d’exclusion de responsabilité signifie que l’utilisateur est invité à entrer un emplacement et qu’il affiche une clause d’exclusion de responsabilité s’il tente de rejeter l’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.

Lorsqu’un utilisateur entre un emplacement manuellement, l’emplacement est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et est stocké dans une table par utilisateur située sur le client. Lorsque l’utilisateur revient à un emplacement précédemment stocké, le client Lync se définit automatiquement à cet emplacement.

<div>


> [!NOTE]
> Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer tous les emplacements stockés dans la table des utilisateurs locaux.



</div>

</div>

<span> </span>

</div>

</div>

</div>

