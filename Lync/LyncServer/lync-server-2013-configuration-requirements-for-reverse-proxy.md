---
title: 'Lync Server 2013: configuration requise pour le proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0367ea79a0f3de6ad716f18aab980e9d9442e148
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Configuration requise pour le proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-05_

Lync Server 2013 impose quelques exigences relatives aux communications du client externe, qui sont ensuite transmises aux services Web externes hébergés sur le directeur, le pool de directeurs, le serveur frontal ou le pool frontal. Le proxy inverse est également responsable de la publication du serveur Office Web Apps, si vous proposez des conférences à vos utilisateurs.

<div>


> [!NOTE]  
> Lync Server 2013 ne spécifie pas de proxy inverse particulier que vous devez utiliser. Lync Server 2013 définit uniquement les exigences opérationnelles que le proxy inverse doit pouvoir exécuter. En règle générale, le proxy inverse que vous avez déjà déployé dans votre infrastructure peut être en mesure de répondre aux exigences.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Configuration requise du proxy inverse

Les opérations fonctionnelles qu’Lync Server 2013 attendent qu’un proxy inverse effectuent:

  - Utiliser le protocole SSL (Secure Socket Layer) et le protocole TLS (Transport Layer Security) implémentés à l’aide de certificats acquis auprès d’une autorité de certification publique pour vous connecter aux services Web externes publiés du directeur, du pool de directeurs, du serveur frontal ou du pool frontal. Le directeur et le serveur frontal peuvent faire partie d’un pool à équilibrage de charge à l’aide d’un dispositif d’équilibrage de la charge matérielle.

  - La possibilité de publier des sites Web internes en utilisant des certificats pour le chiffrement ou de les publier sur une méthode non chiffrée, si nécessaire.

  - Peut publier un site Web hébergé en interne en externe à l’aide d’un nom de domaine complet (FQDN).

  - Capable de publier tout le contenu du site Web hébergé. Par défaut, vous pouvez utiliser la ** / ** directive qui est reconnue par la plupart des serveurs Web afin de dire «publier tout le contenu sur le serveur Web». Vous pouvez également modifier la directive, par exemple **/Uwca/\***, ce qui signifie «publier tout le contenu sous le répertoire virtuel Ucwa».

  - Doit être configuré pour exiger des connexions SSL (Secure Sockets Layer) et/ou TLS (Transport Layer Security) avec des clients qui demandent du contenu à partir d’un site Web publié.

  - Doit accepter les certificats avec les entrées de nom de remplacement de l’objet.

  - Doit être en mesure d’autoriser la liaison d’un certificat à un écouteur ou une interface par le biais duquel le nom de domaine complet des services Web externes sera résolu. Les configurations d’écouteurs sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une même interface ;

  - Doit permettre la configuration de la gestion des en-têtes d’hôte. Dans la plupart des cas, l’en-tête d’hôte d’origine envoyé par le client demandant doit être passé transparent au lieu d’être modifié par le proxy inverse.

  - Le pontage du trafic SSL et TLS d’un port défini en externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443). Le proxy inverse risque de déchiffrer le paquet lors de la réception, puis de rechiffrer le paquet lors de l’envoi.

  - Pontage du trafic TCP non chiffré d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080).

  - Autorisez la configuration de ou acceptez l’authentification NTLM, sans authentification et authentification directe.

</div>

</div>

<span> </span>

</div>

</div>

</div>

