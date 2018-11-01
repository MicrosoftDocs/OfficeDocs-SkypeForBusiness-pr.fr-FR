---
title: "Conf. des app. partenaires dans MLS 2013 et MES 2013"
TOCtitle: "Conf. des app. partenaires dans MLS 2013 et MES 2013"
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49891462
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’authentification de serveur à serveur implique généralement trois entités : les deux serveurs qui doivent communiquer l’un avec l’autre et un serveur d’émission de jetons de sécurité tiers. Si deux serveurs (par exemple Serveur A et Serveur B) doivent communiquer, tous deux commencent en général par contacter un serveur d’émission de jetons et afin d’obtenir un jeton de sécurité approuvé mutuellement. Le Serveur A présente ensuite ce jeton de sécurité au Serveur B (et inversement) afin de prouver son authenticité et sa fiabilité.

Ceci n’est toutefois qu’une règle générale. Lync Server 2013, Microsoft Exchange Server 2013 et Microsoft SharePoint Server 2013 n’ont pas besoin de recourir à un serveur d’émission de jetons tiers pour communiquer, car chacun de ces produits serveurs peut créer des jetons de sécurité susceptibles d’être acceptés par les autres. (Cette fonctionnalité est disponible uniquement dans Lync Server 2013, Exchange 2013 et SharePoint Server 2013. Si vous devez configurer l’authentification de serveur à serveur avec d’autres serveurs, y compris d’autres produits serveurs Microsoft, vous devrez faire appel à un serveur d’émission de jetons tiers.)

Pour configurer l’authentification de serveur à serveur entre Lync Server et Exchange, vous devez effectuer deux opérations : 1) assigner les certificats appropriés à chaque serveur et 2) configurer chaque serveur comme application partenaire de l’autre, ce qui signifie que vous devez configurer Lync Server 2013 comme application partenaire d’Exchange 2013 et configurer Exchange 2013 comme application partenaire de Lync Server 2013.

## Configuration de Lync Server 2013 comme application partenaire d’Exchange 2013

Le moyen le plus simple de configurer Lync Server 2013 comme application partenaire d’Exchange 2013 consiste à exécuter le script Configure-EnterprisePartnerApplication.ps1, un script Windows PowerShell fourni avec Exchange 2013. Pour exécuter ce script, vous devez fournir l’URL du document de métadonnées d’authentification Lync Server ; il s’agit généralement du nom de domaine complet du pool SharePoint suivi du suffixe /metadata/json/1. Par exemple :

    https://atl-cs-001.litwareinc.com/metadata/json/1

Pour configurer Lync Server comme application partenaire, ouvrez Exchange Management Shell et exécutez une commande semblable à la suivante (en supposant qu’Exchange a été installé sur le lecteur C: et qu’il utilise le chemin d’accès de dossier par défaut) :

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur vos serveurs d’accès client et de boîtes aux lettres Exchange. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :

    iisreset atl-exchange-001

Cette commande peut être exécutée depuis Exchange Management Shell ou depuis toute fenêtre de commande exécutée avec des privilèges d’administrateur.

## Configuration d’Exchange 2013 comme application partenaire de Lync Server 2013

Après avoir configuré Lync Server 2013 comme application partenaire d’Exchange 2013, vous devez configurer Exchange comme application partenaire de Lync Server. Vous pouvez pour cela utiliser Lync Server Management Shell et spécifier le document de métadonnées d’authentification pour Exchange ; il s’agit en général de l’URI du service de découverte automatique Exchange suivi du suffixe /metadata/json/1. Par exemple :

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

Dans Lync Server, la configuration des applications partenaires s’effectue à l’aide de l’applet de commande [New-CsPartnerApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPartnerApplication). En plus de spécifier l’URI de métadonnées, vous devez aussi définir le niveau de confiance de l’application sur Total, ce qui permettra à Exchange de se représenter lui-même et tout utilisateur autorisé dans le domaine. Par exemple :

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

En guise d’alternative, vous pouvez créer une application partenaire en copiant et en modifiant le code de script qui se trouve dans la documentation d’authentification de serveur à serveur Lync Server 2013. Pour plus d’informations, voir l’article [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).

Si vous avez réussi à configurer des applications partenaires pour Lync Server et Exchange, cela signifie que vous avez réussi à configurer l’authentification de serveur à serveur entre les deux produits. Lync Server 2013 inclut une applet de commande Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsExStorageConnectivity), qui vous permet de vérifier que l’authentification de serveur à serveur a été configurée correctement et que le service de stockage Lync Server peut se connecter à Exchange 2013. Pour cela, l’applet de commande se connecte à la boîte aux lettres d’un utilisateur Exchange 2013, écrit un élément dans son dossier Historique des conversations, puis supprime éventuellement cet élément.

Pour tester l’intégration de Lync Server 2013 et d’Exchange 2013, exécutez une commande semblable à la suivante depuis Lync Server Management Shell :

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Dans la commande précédente, SipUri représente l’adresse SIP d’un utilisateur disposant d’un compte sur Exchange 2013 ; votre commande échouera s’il ne s’agit pas d’un compte d’utilisateur valide.

Si le test réussit et que la connectivité a été établie, vous pouvez passer à la configuration de fonctionnalités facultatives telles que l’intégration de l’archivage et le magasin de contacts unifié.

