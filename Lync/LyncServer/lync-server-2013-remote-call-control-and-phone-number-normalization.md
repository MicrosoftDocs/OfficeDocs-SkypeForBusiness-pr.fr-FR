---
title: 'Lync Server 2013 : contrôle d’appel distant et normalisation des numéros de téléphone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 211f0f717f7c40895cdbbad75bd98ae0ff90af89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536551"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Les clients Lync téléchargent les règles de normalisation des numéros de téléphone dans le cadre du téléchargement de fichiers du service de carnet d’adresses (ABS). Dans les scénarios de contrôle d’appel distant, ces règles s’appliquent aux appels entrants et sortants de contrôle d’appel distant. Pour les appels entrants vers un utilisateur pour lequel le contrôle d’appel distant est activé, le numéro de téléphone de l’appelant est d’abord normalisé au format E.164 par la passerelle SIP/CSTA ou par un système PBX. Lorsque Lync Server 2013 reçoit l’appel de la passerelle, il effectue une recherche de numéro inversée (RNL) sur le numéro de téléphone de l’appelant par rapport au numéro normalisé de la liste de contacts Microsoft Office Outlook de l’appelé ou de la liste d’adresses globale (LAG) stockée dans le service de carnet d’adresses. Si une correspondance est trouvée, l’appelant est identifié par son nom dans la notification d’appel entrant.

Pour les appels de contrôle d’appel distant sortants, Lync applique les règles de normalisation du service de carnet d’adresses au numéro composé avant d’acheminer l’appel vers la passerelle SIP/CSTA.

Pour plus d’informations sur la création de règles de normalisation des numéros de téléphone pour le contrôle d’appel distant, voir [Dial plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migration des règles de normalisation des numéros de téléphone

Si vous migrez des utilisateurs pour lesquels le contrôle d’appel distant était activé, voir les rubriques suivantes dans la documentation de migration :

  - Pour Lync Server 2010, voir [Migrate Address Book](migrate-address-book.md) dans la documentation de migration.

  - Pour Communications Server 2007 R2, consultez la rubrique [Migrate Address Book](migrate-address-book_1.md) dans la documentation de migration.

</div>

</div>

<span> </span>

</div>

</div>

</div>

