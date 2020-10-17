---
title: 'Lync Server 2013 : configuration des stratégies de démarrage client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 826f732f25996a9f8fcbd708f7e76157a5753a01
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512771"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configuration des stratégies de démarrage client dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

La console de gestion des stratégies de groupe et l’éditeur d’objets de stratégie de groupe sont des outils qui vous permettent de gérer la stratégie de groupe. Les modèles d’administration de la stratégie de groupe Office sont Lync 2013. admx (ADMX) et. adml (ADML), qui contiennent les paramètres de stratégie basés sur le registre que vous configurez pour les objets de stratégie de groupe dans le domaine. Les fichiers ADML sont des compléments spécifiques à la langue pour les fichiers ADMX. Chaque fichier ADMX et ADML contient les paramètres de stratégie pour une seule application Office. Pour plus d’informations, reportez-vous à la rubrique « Office 2013 administrative Template Files (ADMX, ADML) » dans la documentation Office 2013 à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=267516> .

Pour Lync 2013, plusieurs stratégies de démarrage client doivent être configurées avant que les utilisateurs se connectent au serveur pour la première fois. Par exemple, les serveurs et le mode de sécurité par défaut que le client doit utiliser jusqu’à ce que la connexion soit terminée. Vous pouvez utiliser la stratégie de groupe pour établir ces paramètres dans les registres des ordinateurs des utilisateurs avant qu’ils se connectent et commencent à recevoir des paramètres de mise en service intrabande à partir du serveur. Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Lync 2013.

### <a name="group-policy-settings-for-lync-2013"></a>Paramètres des stratégies de groupe de Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre de stratégie de groupe</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Spécifier le serveur<br />
ConfigurationMode</p></td>
<td><p>Indique comment Lync 2013 identifie le transport et le serveur à utiliser lors de la connexion. Dans ce paramètre, vous spécifiez les éléments suivants :</p>
<ul>
<li><p>ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisés par les clients et les contacts fédérés lors de la connexion en dehors du pare-feu externe.</p></li>
<li><p>ServerAddressInternal : spécifie le nom du serveur ou l’adresse IP utilisés lorsque les clients se connectent à l’intérieur du pare-feu de l’organisation.</p></li>
<li><p>Transport : spécifie le protocole TCP (Transmission Control Protocol) ou TLS (Transport Layer Security).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versions de serveur supplémentaires prises en charge<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Spécifie une liste de noms de versions de serveur séparés par des points-virgules sur lesquels Lync Server 2013 se connectera, en plus des versions de serveur prises en charge par défaut.</p></td>
</tr>
<tr class="odd">
<td><p>Désactiver le téléchargement automatique des journaux d’échec de connexion (DisableAutomaticSendTracing)</p></td>
<td><p>Télécharge automatiquement les journaux d’échec de connexion vers Lync Server pour analyse. Aucun journal n’est chargé automatiquement si la connexion réussit. Si cette stratégie n’est pas configurée, voici ce qui se produit :</p>
<dl>
<dt><span></span></dt>
<dd><p>Pour les utilisateurs Lync Online : les journaux d’échec de connexion sont téléchargés automatiquement.</p>
</dd>
<dt><span></span></dt>
<dd><p>Pour les utilisateurs de Lync sur site : une boîte de dialogue de confirmation s’affiche avant le téléchargement.</p>
</dd>
</dl>
<p>Lorsque ce paramètre est désactivé, les journaux de connexion sont téléchargés automatiquement vers le serveur Lync pour les utilisateurs Lync Online et Lync Online. Lorsque ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.</p></td>
</tr>
<tr class="even">
<td><p>Désactiver le secours HTTP pour la connexion SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Empêche Lync Server d’essayer de se connecter au serveur à l’aide du protocole HTTP, si TLS ou TCP ne sont pas disponibles. Par défaut, Lync tente d’abord de se connecter au serveur à l’aide du protocole TLS ou TCP et, si aucune de ces méthodes de transport ne réussit, Lync tente de se connecter à l’aide du protocole HTTP. Utilisez cette stratégie pour désactiver la tentative de remplacement de la connexion HTTP.</p></td>
</tr>
<tr class="odd">
<td><p>Exiger des informations d’identification d’ouverture de session<br />
(DisableNTCredentials)</p></td>
<td><p>Oblige l’utilisateur à fournir des informations d’identification d’ouverture de session pour Lync au lieu d’utiliser automatiquement les informations d’identification Windows lors de la connexion à un serveur SIP.</p></td>
</tr>
<tr class="even">
<td><p>Désactiver la vérification de la version du serveur<br />
(DisableServerCheck)</p></td>
<td><p>Si vous définissez cette stratégie sur 1, empêche Lync de vérifier le nom et la version du serveur avant de se connecter. Par défaut, Lync effectue ces contrôles avant de se connecter.</p></td>
</tr>
<tr class="odd">
<td><p>Activer l’utilisation de BITS pour télécharger les fichiers du service de carnet d’adresses<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permet à Lync d’utiliser le service de transfert intelligent en arrière-plan (BITS) pour télécharger les fichiers des services de carnet d’adresses.</p></td>
</tr>
<tr class="even">
<td><p>Configurer le mode de sécurité SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permet à Lync d’envoyer et de recevoir des messages instantanés de manière plus sécurisée. Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.</p>
<p>Si vous ne configurez pas ce paramètre de stratégie, Lync peut utiliser n’importe quel transport. Toutefois, s’il n’utilise pas le protocole TLS et que le serveur authentifie les utilisateurs, Lync doit utiliser l’authentification NTLM ou Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Délai initial de téléchargement du carnet d’adresses global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Spécifie le délai d’attente avant le téléchargement de la liste d’adresses globale. La valeur par défaut est de 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier de liste d’adresses globale pendant une période aléatoire comprise entre 0 et 60 minutes.</p></td>
</tr>
<tr class="even">
<td><p>Empêcher les utilisateurs d’exécuter Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Empêche les utilisateurs d’exécuter Lync. Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.</p></td>
</tr>
<tr class="odd">
<td><p>Autoriser le stockage des mots de passe utilisateur<br />
SavePassword</p></td>
<td><p>Permet à Lync de stocker des mots de passe.</p></td>
</tr>
<tr class="even">
<td><p>Configurer le mode de compression SIP<br />
(SipCompression)</p></td>
<td><p>Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.</p></td>
</tr>
<tr class="odd">
<td><p>Liste de domaines approuvés<br />
TrustModelData</p></td>
<td><p>Répertorie les domaines approuvés qui ne correspondent pas au préfixe du domaine SIP du client.</p></td>
</tr>
</tbody>
</table>


Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau suivant indique l’ordre de priorité qui est appliqué aux paramètres lorsqu’un conflit se produit.

### <a name="group-policy-precedence"></a>Priorité des stratégies de groupe

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Precedence</th>
<th>Emplacement ou méthode de définition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0,1</p></td>
<td><p>Mise en service intrabande Lync Server 2013</p></td>
</tr>
<tr class="even">
<td><p>n°2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>La boîte de dialogue Lync-options dans Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Pour définir des paramètres de stratégie de groupe à l’aide des fichiers de modèles d’administration Lync 2013

1.  Créez un dossier racine pour contenir tous les fichiers ADMX indépendants de la langue. Par exemple, créez le dossier de racine pour le magasin central sur votre contrôleur de domaine à cet emplacement :
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > Cette procédure suppose que vous souhaitez gérer plusieurs ordinateurs de votre domaine. Dans ce cas, vous stockez les modèles dans un magasin central dans le dossier Sysvol sur le contrôleur de domaine principal. Ceci fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine.

    
    </div>

2.  Créez un sous-dossier pour chaque langue que vous utiliserez. Ces sous-dossiers contiennent les fichiers de ressources ADML propres à une langue. Par exemple, créez un sous-dossier pour l’anglais des États-Unis (en-US) à cet emplacement :
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

