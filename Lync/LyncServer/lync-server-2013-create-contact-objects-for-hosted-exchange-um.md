---
title: 'Lync Server 2013 : créer des objets contact pour la messagerie unifiée Exchange hébergée'
description: 'Lync Server 2013 : créer des objets contact pour la messagerie unifiée Exchange hébergée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9760e2a39b5182f9b5194e364e059bddc6a63d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562300"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Créer des objets contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-24_

La procédure suivante explique comment créer des objets Contact Standard automatique ou Accès abonné pour la messagerie unifiée Exchange hébergée.

Pour plus d’informations, reportez-vous à la rubrique [gestion des objets contact Exchange hébergés dans Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) dans la documentation de planification.

Pour plus d’informations sur la configuration des objets contact, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Avant que les objets contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à ces objets doit être déployée. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-hosted-voice-mail-policies.md">stratégies de messagerie vocale hébergée dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Pour créer des objets Contact Standard automatique ou Accès abonné pour la messagerie unifiée Exchange hébergée

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsExUmContact pour créer les objets Contact requis pour votre déploiement. Exécutez par exemple la commande suivante pour créer un objet Contact Standard automatique ou Accès abonné :
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    Ces exemples définissent les paramètres suivants :
    
      - **SipAddress** indique l’adresse SIP de l’objet Contact. Cette adresse ne doit pas avoir déjà été utilisée pour configurer un objet Contact ou utilisateur dans les services de domaine Active Directory. Cette valeur doit être au format « SIP : \<*SIP address*\> », comme indiqué dans les exemples précédents.
    
      - **RegistrarPool** spécifie le nom de domaine complet du pool sur lequel le service de serveur d’inscriptions est exécuté.
        
        <div class=" ">
        

        > [!NOTE]  
        > Les objets contact de messagerie unifiée Exchange ne peuvent pas être déplacés vers des pools qui font partie de déploiements Lync Server 2013 antérieurs à Lync Server 2013.

        
        </div>
    
      - **OU** spécifies l’unité d’organisation Active Directory dans laquelle cet objet Contact sera situé.
    
      - **DisplayNumber** spécifie le numéro de téléphone de l’objet Contact. Le numéro de téléphone de chaque objet Contact doit être unique.
    
      - **AutoAttendant** indique si l’objet Contact est un standard automatique. Le standard automatique fournit un ensemble d’invites vocales qui permettent aux appelants de naviguer dans le système téléphonique et de joindre la personne désirée. Si ce paramètre est défini sur la valeur **False** (par défaut), cela indique un objet Contact Accès abonné.

</div>

</div>

<span> </span>

</div>

</div>

</div>

