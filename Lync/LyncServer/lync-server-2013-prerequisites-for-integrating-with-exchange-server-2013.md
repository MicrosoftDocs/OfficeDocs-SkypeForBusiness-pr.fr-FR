---
title: 'Lync Server 2013 : conditions requises pour l’intégration à Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 686d7d5d65af28127ad95b2911962d707887029a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Conditions préalables à l’intégration de Microsoft Lync Server 2013 et de Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-22_

Avant de pouvoir intégrer Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, vous devez vous assurer que toutes les étapes préalables ont été effectuées. Comme vous pouvez vous y attendre, l’intégration ne peut avoir lieu que lorsque Exchange 2013 et Lync Server 2013 sont entièrement installés et en cours d’exécution. Pour plus d’informations sur l’installation d’Exchange, consultez la documentation sur la [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539)planification et le déploiement d’Exchange 2013 à l’adresse. Pour plus d’informations sur l’installation de Lync Server 2013, voir la documentation [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806)sur la planification et le déploiement à l’adresse.

Une fois les serveurs opérationnels, vous devez attribuer des certificats d’authentification de serveur à serveur à Lync Server 2013 et à Exchange 2013 ; ces certificats permettent à Lync Server et Exchange d’échanger des informations et de communiquer les uns avec les autres. Lorsque vous installez Exchange 2013, un certificat auto-signé avec le nom certificat d’authentification Microsoft Exchange Server est créé pour vous. Ce certificat, qui se trouve dans le magasin de certificats de l’ordinateur local, doit être utilisé pour l’authentification de serveur à serveur sur Exchange 2013. Pour plus d’informations sur l’attribution de certificats dans Exchange 2013, voir « Configurer le flux de messagerie [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540)et l’accès au client » à l’adresse.

Pour Lync Server 2013, vous pouvez utiliser un certificat Lync Server existant comme certificat d’authentification de serveur à serveur ; par exemple, votre certificat par défaut peut également être utilisé comme certificat OAuthTokenIssuer. Lync Server 2013 vous permet d’utiliser n’importe quel certificat de serveur Web comme certificat pour l’authentification de serveur à serveur, à condition que :

  - Le certificat inclut le nom de votre domaine SIP dans le champ Subject.

  - Le même certificat est configuré comme certificat OAuthTokenIssuer sur tous vos serveurs frontaux.

  - Le certificat a une longueur d’au moins 2048 bits.

Pour plus d’informations sur les certificats d’authentification de serveur à serveur pour Microsoft Lync Server 2013, reportez-vous [à la rubrique Assigning a Server-to-Server Authentication Certificate to Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Une fois les certificats attribués, vous devez configurer le service de découverte automatique sur Exchange 2013. Dans Exchange 2013, le service de découverte automatique configure les profils utilisateur et permet d’accéder aux services Exchange lorsque les utilisateurs se connectent au système. Les utilisateurs présentent le service de découverte automatique avec leur adresse de messagerie et leur mot de passe ; en retour, les services fournissent à l’utilisateur des informations telles que :

  - Les informations de connexion pour la connectivité interne et externe à Exchange 2013.

  - Emplacement du serveur de boîtes aux lettres de l’utilisateur.

  - URL pour les fonctionnalités Outlook telles que les informations de disponibilité, la messagerie unifiée et le carnet d’adresses en mode hors connexion.

  - Paramètres du serveur Outlook Anywhere.

Le service de découverte automatique doit être configuré pour pouvoir intégrer Lync Server 2013 et Exchange 2013. Vous pouvez vérifier si le service de découverte automatique a été configuré en exécutant la commande suivante à partir de l’environnement de commande Exchange Management Shell et en vérifiant la valeur de la propriété AutoDiscoverServiceInternalUri :

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Si cette valeur est vide, vous devez affecter un URI au service de découverte automatique. En règle générale, cet URI ressemblera à ceci :

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Vous pouvez attribuer l’URI de découverte automatique en exécutant une commande semblable à celle-ci :

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Pour plus d’informations sur le service de découverte automatique, voir « Understanding the Autodiscover Service » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542).

Une fois que le service de découverte automatique a été configuré, vous devez modifier les paramètres de configuration OAuth de Lync Server ; Cela garantit que Lync Server sait où trouver le service de découverte automatique. Pour modifier les paramètres de configuration OAuth dans Lync Server 2013, exécutez la commande suivante à partir de Lync Server Management Shell. Lors de l’exécution de cette commande, vérifiez que vous spécifiez l’URI pour le service de découverte automatique exécuté sur votre serveur Exchange et que vous utilisez **autodiscover. svc** pour pointer vers l’emplacement de service au lieu de **autodiscover. xml** (qui pointe vers le fichier XML utilisé par le service) :

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Le paramètre Identity de la commande précédente est facultatif ; Cela est dû au fait que Lync Server vous permet d’avoir une seule collection globale de paramètres de configuration OAuth. Cela signifie, entre autres, que vous pouvez configurer l’URL de découverte automatique à l’aide de cette commande légèrement plus simple :<BR>Set-applet csoauthconfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Si vous n’êtes pas familiarisé avec cette technologie, OAuth est un protocole d’autorisation standard utilisé par un certain nombre de sites principaux. Avec OAuth, les informations d’identification de l’utilisateur et les mots de passe ne sont pas transmis d’un ordinateur à un autre. Au lieu de cela, l’authentification et l’autorisation sont basées sur l’échange de jetons de sécurité ; Ces jetons accordent l’accès à un ensemble spécifique de ressources pour une durée spécifique.



</div>

En plus de configurer le service de découverte automatique, vous devez également créer un enregistrement DNS pour le service qui pointe vers votre serveur Exchange. Par exemple, si votre service de découverte automatique se trouve dans autodiscover.litwareinc.com, vous devez créer un enregistrement DNS pour autodiscover.litwareinc.com qui se traduit par le nom de domaine complet de votre serveur Exchange (par exemple, atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

