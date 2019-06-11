---
title: 'Lync Server 2013: configuration des stratégies de démarrage de clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Configuration de stratégies de démarrage de clients dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

La Console de gestion des stratégies de groupe et l’Éditeur d’objets de stratégie de groupe sont des outils que vous utilisez pour gérer la stratégie de groupe. Inclus dans le modèle d’administration de la stratégie de groupe Office sont les modèles d’administration de Lync 2013. admx (ADMX) et. adml (ADML) qui contiennent les paramètres de stratégie de Registre configurés pour les objets de stratégie de groupe du domaine. Les fichiers ADML sont des compléments spécifiques à une langue pour les fichiers ADMX. Chaque fichier ADMX et ADML contient les paramètres de stratégie d’une seule application Office. Pour plus d’informations, reportez-vous à la section «fichiers de modèles d’administration Office 2013 (ADMX <http://go.microsoft.com/fwlink/p/?linkid=267516>, ADML)» dans la documentation Office 2013 à l’adresse.

Pour Lync 2013, il existe plusieurs stratégies de démarrage de clients que vous devez envisager de configurer avant la première connexion des utilisateurs au serveur. C’est le cas, par exemple, des serveurs par défaut et du mode de sécurité que le client doit utiliser jusqu’à ce que l’authentification soit terminée. Vous pouvez utiliser la stratégie de groupe pour établir ces paramètres dans le Registre des ordinateurs des utilisateurs avant qu’ils se connectent et commencent à recevoir des paramètres de mise en service intrabande en provenance du serveur. Le tableau suivant répertorie les paramètres de stratégie de groupe disponibles pour Lync 2013.

### <a name="group-policy-settings-for-lync-2013"></a>Paramètres de stratégie de groupe pour Lync 2013

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
<td><p>Spécifie la façon dont Lync 2013 identifie le transport et le serveur à utiliser lors de la connexion. Dans ce paramètre, spécifiez les valeurs suivantes :</p>
<ul>
<li><p>ServerAddressExternal : spécifie le nom du serveur ou l’adresse IP utilisé par les clients et les contacts fédérés lors de la connexion de l’extérieur du pare-feu externe.</p></li>
<li><p>ServerAddressInternal : spécifie le nom ou l’adresse IP du serveur utilisé quand les clients se connectent de l’intérieur du pare-feu de l’organisation.</p></li>
<li><p>Transfert : spécifie le protocole TCP (Transmission Control Protocol) ou TLS (Transport Layer Security).</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Versions serveur supplémentaires prises en charge<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Spécifie une liste de noms de version de serveur séparés par des points-virgules que Lync Server 2013 utilisera en plus des versions de serveur prises en charge par défaut.</p></td>
</tr>
<tr class="odd">
<td><p>Désactiver le téléchargement automatique des journaux d’échec de connexion (DisableAutomaticSendTracing)</p></td>
<td><p>Charge automatiquement les journaux d’échecs de connexion à Lync Server pour analyse. Aucun journal n’est téléchargé automatiquement si l’authentification réussit. Si cette stratégie n’est pas configurée, voici ce qui se produit :</p>
<dl>
<dt><span></span></dt>
<dd><p>Pour les utilisateurs de Lync Online: les journaux d’échecs de connexion sont automatiquement téléchargés.</p>
</dd>
<dt><span></span></dt>
<dd><p>Pour les utilisateurs Lync local: une boîte de dialogue de confirmation s’affiche à l’utilisateur avant le chargement.</p>
</dd>
</dl>
<p>Lorsque ce paramètre est désactivé, les journaux de connexion sont automatiquement téléchargés sur le serveur Lync pour les utilisateurs Lync Online et Lync Online. Lorsque ce paramètre est activé, les journaux de connexion ne sont jamais téléchargés automatiquement.</p></td>
</tr>
<tr class="even">
<td><p>Désactiver le secours HTTP pour la connexion SIP<br />
(DisableHttpConnect)</p></td>
<td><p>Empêche Lync Server d’essayer de se connecter au serveur à l’aide du protocole HTTP, si TLS ou TCP ne sont pas disponibles. Par défaut, Lync tente d’abord de se connecter au serveur à l’aide du protocole TLS ou du protocole TCP et, si aucune de ces méthodes de transport n’est réussie, Lync essaie de se connecter à l’aide de HTTP. Utilisez cette stratégie pour désactiver la tentative de connexion HTTP de secours.</p></td>
</tr>
<tr class="odd">
<td><p>Nécessiter les informations d’identification d’ouverture de session<br />
(DisableNTCredentials)</p></td>
<td><p>Nécessite que l’utilisateur fournit des informations d’identification pour Lync au lieu d’utiliser automatiquement les informations d’identification Windows lors de la connexion à un serveur SIP.</p></td>
</tr>
<tr class="even">
<td><p>Vérification de la version du serveur<br />
(DisableServerCheck)</p></td>
<td><p>Si vous affectez la valeur 1 à cette stratégie, vous empêchez Lync de vérifier le nom et la version du serveur avant de vous connecter. Par défaut, Lync effectue ces vérifications avant la connexion.</p></td>
</tr>
<tr class="odd">
<td><p>Activer l’utilisation de BITS pour télécharger des fichiers du service de carnet d’adresses<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Permet à Lync d’utiliser le service de transfert intelligent en arrière-plan (BITS) pour télécharger les fichiers du service de carnet d’adresses.</p></td>
</tr>
<tr class="even">
<td><p>Configurer le mode de sécurité SIP<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Permet à Lync d’envoyer et de recevoir des messages instantanés plus en toute sécurité. Cette stratégie n’a pas d’incidence sur les services Windows .NET ou Microsoft Exchange Server.</p>
<p>Si vous ne configurez pas ce paramètre de stratégie, Lync peut utiliser n’importe quel transport. Mais s’il n’utilise pas TLS et si le serveur authentifie les utilisateurs, Lync doit utiliser l’authentification NTLM ou Kerberos.</p></td>
</tr>
<tr class="odd">
<td><p>Délai initial de téléchargement du carnet d’adresses global<br />
(GalDownloadInitialDelay)</p></td>
<td><p>Spécifie le délai d’attente avant que la liste d’adresses globale soit téléchargée. La valeur par défaut est de 60 minutes, ce qui signifie que le serveur retarde le téléchargement du fichier de la liste d’adresses globale pendant une période aléatoire comprise entre 0 et 60 minutes.</p></td>
</tr>
<tr class="even">
<td><p>Empêcher les utilisateurs d’exécuter Microsoft Lync<br />
(PreventRun)</p></td>
<td><p>Empêche les utilisateurs d’exécuter Lync. Vous pouvez configurer ce paramètre de stratégie sous Configuration ordinateur et sous Configuration utilisateur, mais le paramètre de stratégie sous Configuration ordinateur est prioritaire.</p></td>
</tr>
<tr class="odd">
<td><p>Autoriser le stockage des mots de passe d’utilisateur<br />
(SavePassword)</p></td>
<td><p>Permet à Lync d’enregistrer les mots de passe.</p></td>
</tr>
<tr class="even">
<td><p>Configurer le mode de compression SIP<br />
(SipCompression)</p></td>
<td><p>Spécifie les conditions d’activation de la compression SIP. Par défaut, la compression SIP est activée en fonction de la vitesse de la carte réseau. Notez que la définition de cette stratégie peut augmenter le délai de connexion.</p></td>
</tr>
<tr class="odd">
<td><p>Liste des domaines approuvés<br />
TrustModelData</p></td>
<td><p>Répertorie les domaines approuvés qui ne correspondent pas au préfixe du domaine SIP du client.</p></td>
</tr>
</tbody>
</table>


Les stratégies configurées sur le serveur prévalent toujours sur les paramètres de stratégie de groupe et sur les options du client configurées par l’utilisateur. Le tableau ci-dessous indique l’ordre de priorité appliqué aux paramètres en cas de conflit.

### <a name="group-policy-precedence"></a>Priorité des stratégies de groupe

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Priorité</th>
<th>Emplacement ou méthode de définition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Mise en service de Lync Server 2013 intrabande</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Boîte de dialogue Lync-options dans Lync 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Pour définir les paramètres de stratégie de groupe à l’aide des fichiers de modèles d’administration de Lync 2013

1.  Créez un dossier de niveau racine destiné à contenir tous les fichiers ADMX indépendants de la langue. Par exemple, créez le dossier racine du magasin central sur votre contrôleur de domaine à cet emplacement :
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > Pour cette procédure, nous supposons que vous voulez gérer plusieurs ordinateurs de votre domaine. Dans ce cas, enregistrez les modèles dans un magasin central dans le dossier Sysvol sur le contrôleur de domaine principal. Cela fournit un emplacement de stockage central répliqué pour les modèles d’administration de domaine.

    
    </div>

2.  Créez un sous-dossier pour chaque langue à utiliser. Ces sous-dossiers contiennent les fichiers de ressources ADML spécifiques à une langue. Par exemple, créez un sous-dossier pour l’anglais américain (EN-US) à l’emplacement suivant :
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

