---
title: 'Lync Server 2013: prérequis pour l’intégration à Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51bc3ce48756f746b2f2f5c0ce65d08567fea74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Conditions préalables à l’intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-04-22_

Pour pouvoir intégrer Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, vous devez vous assurer que toutes les étapes préalables ont été effectuées. Comme vous pouvez vous attendre, l’intégration ne peut pas être effectuée tant que Exchange 2013 et Lync Server 2013 ne sont pas entièrement installés et en cours d’exécution. Pour plus d’informations sur l’installation d’Exchange, voir la documentation relative à [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)la planification et au déploiement d’Exchange 2013 à l’adresse. Pour plus d’informations sur l’installation de Lync Server 2013, consultez la documentation [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)de planification et de déploiement à l’adresse.

Une fois les serveurs opérationnels, vous devez attribuer des certificats d’authentification de serveur à serveur à Lync Server 2013 et Exchange 2013. ces certificats permettent à Lync Server et Exchange d’échanger des informations et de communiquer entre eux. Lorsque vous installez Exchange 2013, un certificat auto-signé avec le nom Microsoft Exchange Server auth est créé pour vous. Ce certificat, qui se trouve dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification serveur à serveur sur Exchange 2013. Pour plus d’informations sur l’attribution de certificats dans Exchange 2013, voir «Configurer le flux de messagerie [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)et l’accès client» à l’adresse.

Pour Lync Server 2013, vous pouvez utiliser un certificat Lync Server existant comme certificat d’authentification de serveur à serveur. par exemple, vous pouvez également utiliser votre certificat par défaut comme certificat OAuthTokenIssuer. Lync Server 2013 vous permet d’utiliser n’importe quel certificat de serveur Web comme certificat d’authentification de serveur à serveur pour les éléments suivants:

  - le certificat inclue le nom de votre domaine SIP dans le champ Objet ;

  - le même certificat soit configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux ;

  - la longueur du certificat soit d’au moins 2 048 bits.

Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Microsoft Lync Server 2013, voir [affectation d’un certificat d’authentification de serveur à serveur à Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Une fois les certificats attribués, vous devez configurer le service de découverte automatique sur Exchange 2013. Dans Exchange 2013, le service de découverte automatique configure les profils utilisateur et donne accès aux services Exchange lorsque les utilisateurs ouvrent une session sur le système. Les utilisateurs indiquent leur adresse de messagerie et leur mot de passe au service de découverte automatique ; le service fournit en retour à l’utilisateur des informations telles que :

  - Informations de connexion pour la connectivité interne et externe à Exchange 2013.

  - l’emplacement du serveur de boîte aux lettres de l’utilisateur ;

  - les URL pour les fonctionnalités Outlook telles que les informations sur la disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion ;

  - les paramètres de serveur d’Outlook Anywhere.

Le service de découverte automatique doit être configuré pour pouvoir intégrer Lync Server 2013 et Exchange 2013. Vous pouvez vérifier si le service de découverte automatique a ou non été configuré en exécutant la commande suivante à partir d’Exchange Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Si cette valeur est vide, vous devez attribuer un URI au service de découverte automatique. Cet URI ressemble généralement à ceci :

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Pour plus d’informations sur le service de découverte automatique, voir «présentation du service de [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)découverte automatique» à l’adresse.

Une fois le service de découverte automatique configuré, vous devez modifier les paramètres de configuration OAuth de Lync Server. Cela permet à Lync Server de savoir où trouver le service de découverte automatique. Pour modifier les paramètres de configuration OAuth dans Lync Server 2013, exécutez la commande suivante à partir de Lync Server Management Shell. Lorsque vous exécutez cette commande, veillez à spécifier l’URI vers le service de découverte automatique qui s’exécute sur votre serveur Exchange, et que vous utilisez la **découverte automatique. svc** pour pointer sur l’emplacement du service au lieu de la **découverte automatique. xml** (qui pointe vers le fichier XML utilisé par le service):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Le paramètre Identity de la commande précédente est facultatif; C’est parce que Lync Server vous permet uniquement d’avoir une collection globale unique de paramètres de configuration OAuth. Entre autres choses, cela signifie que vous pouvez configurer l’URL de découverte automatique à l’aide de cette commande légèrement plus simple:<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Si vous ne connaissez pas cette technologie, OAuth est un protocole d’autorisation standard utilisé par nombre des plus importants sites web. Grâce à OAuth, les informations d’identification et les mots de passe d’utilisateur ne sont pas transmis d’un ordinateur à un autre. L’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité. Ces jetons octroient l’accès à un ensemble de ressources spécifique pour une durée spécifique.



</div>

En plus de configurer le service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre serveur Exchange. Par exemple, si votre service de découverte automatique se trouve dans autodiscover.litwareinc.com, vous devez créer un enregistrement DNS pour autodiscover.litwareinc.com résolu sur le nom de domaine complet de votre serveur Exchange (par exemple, atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

