---
title: 'Lync Server 2013 : configuration requise pour le proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13026da5515615610c960fe4648d5c58f64f99fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Configuration requise pour le proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-05_

Lync Server 2013 impose quelques exigences sur les communications à partir du client externe, qui sont ensuite transmises aux services Web externes hébergés sur le directeur, le pool Directeur, le serveur frontal ou le pool frontal. Le proxy inverse est également responsable de la publication d’Office Web Apps Server, si vous proposez des conférences à vos utilisateurs.

<div>


> [!NOTE]  
> Lync Server 2013 ne spécifie pas un proxy inverse particulier que vous devez utiliser. Lync Server 2013 définit uniquement les exigences opérationnelles que le proxy inverse doit être en mesure de faire. En règle générale, le proxy inverse que vous avez déjà déployé dans votre infrastructure peut répondre aux exigences.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Exigences relatives au proxy inverse

Les opérations fonctionnelles que Lync Server 2013 attend qu’un proxy inverse effectuent sont les suivantes :

  - Utilisez les protocoles SSL (Secure Socket Layer) et TLS (Transport Layer Security) implémentés à l’aide de certificats acquis auprès d’une autorité de certification publique pour se connecter aux services Web externes publiés du directeur, du pool Directeur, du serveur frontal ou du pool frontal. Le directeur et le serveur frontal peuvent se trouver dans un pool à charge équilibrée à l’aide d’programmes d’équilibrage de la charge matérielle.

  - En mesure de publier des sites Web internes à l’aide de certificats pour le chiffrement, ou de les publier sur des moyens non chiffrés, si nécessaire.

  - En mesure de publier un site Web hébergé en interne de façon externe à l’aide d’un nom de domaine complet (FQDN).

  - En mesure de publier tout le contenu du site Web hébergé. Par défaut, vous pouvez utiliser la ** / ** directive, qui est reconnue par la plupart des serveurs Web comme signifiant « publier tout le contenu sur le serveur Web ». Vous pouvez également modifier la directive (par exemple, **/Uwca/\***, ce qui signifie « publier tout le contenu sous le répertoire virtuel Ucwa ».

  - Doit être configurable pour exiger des connexions SSL (Secure Sockets Layer) et/ou TLS (Transport Layer Security) avec des clients qui demandent du contenu à partir d’un site Web publié.

  - Doit accepter les certificats avec des entrées de l’autre nom de l’objet (SAN).

  - Doit pouvoir autoriser la liaison d’un certificat à un écouteur ou une interface par le biais duquel le nom de domaine complet des services Web externes est résolu. Les configurations de l’écouteur sont préférables aux interfaces. De nombreux écouteurs peuvent être configurés sur une seule interface.

  - Doit autoriser la configuration de la gestion des en-têtes d’hôte. Souvent, l’en-tête d’hôte d’origine envoyé par le client demandeur doit être passé de manière transparente, au lieu d’être modifié par le proxy inverse.

  - Le pontage du trafic SSL et TLS à partir d’un port défini de manière externe (par exemple, TCP 443) vers un autre port défini (par exemple, TCP 4443). Le proxy inverse peut déchiffrer le paquet lors de sa réception, puis rechiffrer le paquet lors de l’envoi.

  - Le pontage du trafic TCP non chiffré à partir d’un port (par exemple, TCP 80) vers un autre (par exemple, TCP 8080).

  - Autorisez la configuration ou acceptez, l’authentification NTLM, aucune authentification et authentification directe.

</div>

</div>

<span> </span>

</div>

</div>

</div>

