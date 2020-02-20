---
title: Configuration des applications partenaires dans Lync Server 2013 et Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fca5fe648ecfb00c7ef7bcb84948a68e4386bbf3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-12_

L’authentification de serveur à serveur implique généralement trois entités : les deux serveurs qui doivent communiquer l’un avec l’autre et un serveur d’émission de jetons de sécurité tiers. Si deux serveurs (par exemple Serveur A et Serveur B) doivent communiquer, tous deux commencent en général par contacter un serveur d’émission de jetons et afin d’obtenir un jeton de sécurité approuvé mutuellement. Le Serveur A présente ensuite ce jeton de sécurité au Serveur B (et inversement) afin de prouver son authenticité et sa fiabilité.

Ceci n’est toutefois qu’une règle générale. Lync Server 2013, Microsoft Exchange Server 2013 et Microsoft SharePoint Server 2013 n’ont pas besoin d’utiliser un serveur de jetons tiers lors de la communication les uns avec les autres ; Cela est dû au fait que ces produits serveur peuvent créer des jetons de sécurité qui peuvent être acceptés les uns avec les autres sans avoir besoin d’un serveur de jetons distinct. (Cette fonctionnalité est disponible uniquement dans Lync Server 2013, Exchange 2013 et SharePoint Server 2013. Si vous devez configurer l’authentification de serveur à serveur avec d’autres serveurs, y compris d’autres produits serveurs Microsoft, vous devrez faire appel à un serveur d’émission de jetons tiers.)

Pour configurer l’authentification de serveur à serveur entre Lync Server et Exchange, vous devez effectuer deux opérations : 1) vous devez affecter les certificats appropriés à chaque serveur ; et, 2) vous devez configurer chaque serveur de sorte qu’il soit une application partenaire de l’autre serveur : cela signifie que vous devez configurer Lync Server 2013 comme application partenaire pour Exchange 2013 et vous devez configurer Exchange 2013 comme application partenaire pour Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configuration de Lync Server 2013 comme application partenaire pour Exchange 2013

Le moyen le plus simple de configurer Lync Server 2013 en tant qu’application partenaire avec Exchange 2013 est d’exécuter le script configure-enterprisepartnerapplication. ps1, un script Windows PowerShell fourni avec Exchange 2013. Pour exécuter ce script, vous devez fournir l’URL du document de métadonnées d’authentification Lync Server ; Il s’agit généralement du nom de domaine complet du pool Lync Server 2013 suivi du suffixe/Metadata/JSON/1. Par exemple :

    https://atl-cs-001.litwareinc.com/metadata/json/1

Pour configurer Lync Server en tant qu’application partenaire, ouvrez l’environnement de commande Exchange Management Shell et exécutez une commande semblable à celle-ci (en supposant qu’Exchange a été installé sur le lecteur C : et qu’il utilise le chemin d’accès au dossier par défaut) :

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer les services Internet (IIS) sur vos serveurs de boîtes aux lettres et d’accès au client Exchange. Vous pouvez redémarrer les services Internet (IIS) à l’aide d’une commande ressemblant à celle-ci, qui permet de redémarrer le service sur l’ordinateur atl-exchange-001 :

    iisreset atl-exchange-001

Cette commande peut être exécutée à partir de l’environnement de commande Exchange Management Shell ou de toute autre fenêtre de commande exécutée sous les privilèges d’administrateur.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configuration d’Exchange 2013 comme application partenaire pour Lync Server 2013

Une fois que vous avez configuré Lync Server 2013 comme application partenaire pour Exchange 2013, vous devez configurer Exchange comme application partenaire pour Lync Server. Ceci peut être réalisé à l’aide de Lync Server Management Shell et en spécifiant le document de métadonnées d’authentification pour Exchange ; Il s’agit généralement de l’URI du service de découverte automatique Exchange suivi du suffixe/Metadata/JSON/1. Par exemple :

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

Dans Lync Server, les applications partenaires sont configurées à l’aide de la cmdlet [New-applet cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) . En plus de spécifier l’URI de métadonnées, vous devez également définir le niveau de confiance Full pour l’application ; Cela permet à Exchange de se représenter lui-même et tout utilisateur autorisé dans le domaine. Par exemple :

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Vous pouvez également créer une application partenaire en copiant et en modifiant le code de script figurant dans la documentation de l’authentification de serveur à serveur de Lync Server 2013. Pour plus d’informations, reportez-vous à l’article [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Si vous avez réussi à configurer les applications partenaires pour Lync Server et Exchange, cela signifie que vous avez également réussi à configurer l’authentification de serveur à serveur entre les deux produits. Lync Server 2013 inclut une applet de commande Windows PowerShell, [test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), qui vous permet de vérifier que l’authentification de serveur à serveur a été correctement configurée et que le service de stockage Lync Server peut se connecter à Exchange 2013. L’applet de commande effectue cette opération en se connectant à la boîte aux lettres d’un utilisateur Exchange 2013, en écrivant un élément dans le dossier historique des conversations de cet utilisateur, puis en supprimant éventuellement cet élément.

Pour tester l’intégration de Lync Server 2013 et Exchange 2013, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Dans la commande précédente, SipUri représente l’adresse SIP d’un utilisateur disposant d’un compte sur Exchange 2013. votre commande échouera dans ce n’est pas un compte d’utilisateur valide.

Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.

</div>

</div>

<span> </span>

</div>

</div>

</div>

