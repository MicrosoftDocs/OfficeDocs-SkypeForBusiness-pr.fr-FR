---
title: Configuration des applications partenaires dans Lync Server 2013 et Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-12_

L’authentification de serveur à serveur implique généralement trois entités: les deux serveurs qui doivent communiquer entre eux et un serveur d’jetons de sécurité tiers. Si deux serveurs (par exemple, serveur A et serveur B) doivent communiquer, chacun de ces serveurs doit généralement commencer par contacter un serveur jeton et obtenir un jeton de sécurité digne de confiance. Le serveur A doit alors présenter ce jeton de sécurité au serveur B (et inversement) pour garantir son authenticité et sa fiabilité.

Néanmoins, il s’agit d’une règle générale. Lync Server 2013, Microsoft Exchange Server 2013 et Microsoft SharePoint Server 2013 n’ont pas besoin d’utiliser un serveur jeton tiers lors de la communication entre eux. ce n’est pas parce que ces produits serveur peuvent créer des jetons de sécurité qui peuvent être acceptés l’un de l’autre sans qu’il soit nécessaire de recourir à un serveur jeton distinct. (Cette fonctionnalité est disponible uniquement dans Lync Server 2013, Exchange 2013 et SharePoint Server 2013. Si vous avez besoin de configurer l’authentification serveur à serveur avec d’autres serveurs, y compris d’autres produits Microsoft Server, vous devez le faire à l’aide d’un serveur de jetons tiers.)

Pour configurer l’authentification de serveur à serveur entre Lync Server et Exchange, vous devez effectuer deux opérations: 1) vous devez attribuer les certificats appropriés à chaque serveur. et 2) vous devez configurer chaque serveur pour qu’il soit une application partenaire de l’autre serveur: autrement dit, vous devez configurer Lync Server 2013 de manière à ce qu’il s’agit d’une application partenaire pour Exchange 2013 et vous devez configurer Exchange 2013 pour être une application partenaire pour Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configuration de Lync Server 2013 en tant qu’application partenaire pour Exchange 2013

Le moyen le plus simple de configurer Lync Server 2013 comme application partenaire avec Exchange 2013 consiste à exécuter le script Configure-EnterprisePartnerApplication. ps1, un script Windows PowerShell fourni avec Exchange 2013. Pour exécuter ce script, vous devez fournir l’URL du document de métadonnées d’authentification de Lync Server. Il s’agit généralement du nom de domaine complet du pool Lync Server 2013 suivi du suffixe/Metadata/JSON/1. Par exemple :

    https://atl-cs-001.litwareinc.com/metadata/json/1

Pour configurer Lync Server en tant qu’application partenaire, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en partant du principe que Exchange a été installé sur le lecteur C, et qu’il utilise le chemin de dossier par défaut):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur votre boîte aux lettres Exchange et les serveurs d’accès au client. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :

    iisreset atl-exchange-001

Vous pouvez exécuter cette commande à partir de Exchange Management Shell ou de n’importe quelle autre fenêtre de commande sous privilèges d’administrateur.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configuration d’Exchange 2013 pour être une application partenaire pour Lync Server 2013

Une fois que vous avez configuré Lync Server 2013 comme application partenaire pour Exchange 2013, vous devez ensuite configurer Exchange en tant qu’application partenaire de Lync Server. Vous pouvez effectuer cette opération à l’aide de Lync Server Management Shell et en spécifiant le document de métadonnées d’authentification pour Exchange. Il s’agit généralement de l’URI du service de découverte automatique Exchange suivi du suffixe/Metadata/JSON/1. Par exemple :

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

Dans Lync Server, les applications partenaires sont configurées à l’aide de l’applet [de nouvelle applet de nouveau-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) . En plus de spécifier l’URI de métadonnées, vous devez également définir le niveau de confiance application sur complet. Cela permet à Exchange de représenter eux-mêmes et tout utilisateur autorisé du domaine. Par exemple :

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Vous pouvez également créer une application partenaire en copiant et en modifiant le code de script figurant dans la documentation relative à l’authentification serveur et serveur Lync Server 2013. Pour plus d’informations, reportez-vous à l’article [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenariat dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Si vous avez correctement configuré des applications de partenariat pour Lync Server et Exchange, cela signifie que vous avez correctement configuré l’authentification de serveur à serveur entre les deux produits. Lync Server 2013 inclut une cmdlet Windows PowerShell, [test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), qui vous permet de vérifier que l’authentification de serveur à serveur est correctement configurée et que le service de stockage Lync Server peut se connecter à Exchange 2013. Cette applet de commande permet de se connecter à la boîte aux lettres d’un utilisateur Exchange 2013, d’écrire un élément dans le dossier historique des conversations pour cet utilisateur, puis de supprimer cet élément éventuellement.

Pour tester l’intégration de Lync Server 2013 et Exchange 2013, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Dans la commande précédente, le SipUri représente l’adresse SIP d’un utilisateur disposant d’un compte sur Exchange 2013; Il n’existe pas de compte d’utilisateur valide pour votre commande.

Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.

</div>

</div>

<span> </span>

</div>

</div>

</div>

