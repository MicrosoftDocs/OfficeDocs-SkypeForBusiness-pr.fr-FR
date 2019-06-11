---
title: 'Lync Server 2013: créer une collection de paramètres de configuration de Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c578fd670661413df0a8fb81cb1ce0316db13f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>Créer une collection de paramètres de configuration de Trunk dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. Ces paramètres spécifient, par exemple :

  - si la déviation du trafic multimédia doit être activée sur les jonctions ;

  - Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.

  - Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de Trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

Lors de la création des paramètres de configuration de Trunk SIP à l’aide du panneau de configuration de Lync Server, les options suivantes sont disponibles:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre de l’interface utilisateur</th>
<th>Paramètre PowerShell</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>Identity</p></td>
<td><p>Identificateur unique de la collection. Cette propriété est en lecture seule. Vous ne pouvez pas modifier l’identité d’une collection de paramètres de configuration des jonctions.</p></td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>Description</p></td>
<td><p>Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).</p></td>
</tr>
<tr class="odd">
<td><p>Nombre maximal de boîtes de dialogue préliminaires prises en charge</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Nombre maximal de réponses dirigées qu’une passerelle RTC, un système IP-PBX ou un contrôleur de session en périphérie côté fournisseur de services peut recevoir à une invitation envoyée au serveur de médiation.</p></td>
</tr>
<tr class="even">
<td><p>Niveau de prise en charge du chiffrement</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle RTC, le système IP-PBX ou le contrôleur SBC (Session Border Controller) côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. La configuration de média est définie à l’aide de la cmdlet <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> et de <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</p>
<p>Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>Obligatoire : le chiffrement SRTP doit être utilisé.</p></li>
<li><p>Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge.</p></li>
<li><p>Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.</p></li>
</ul>
<p>SRTPMode n’est utilisé que si la passerelle est configurée de manière à utiliser le protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.</p></td>
</tr>
<tr class="odd">
<td><p>Prise en charge de la référence</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Si ce paramètre défini sur <strong>Activer la référence d’appel vers la passerelle</strong>, cela indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.</p>
<p>S’il est défini sur <strong>Activer la référence avec un contrôle d’appel tiers</strong>, cela indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé. 3PCC est également connu sous &quot;le nom de contrôle&quot; tiers et se produit lorsqu’un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel de la personne a à la personne B).</p></td>
</tr>
<tr class="even">
<td><p>Activer la déviation du trafic multimédia</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indique si la déviation du trafic multimédia est activée pour cette jonction. La déviation du trafic multimédia ne peut être activée que si <strong>Traitement multimédia centralisé</strong> est activé également.</p></td>
</tr>
<tr class="odd">
<td><p>Traitement multimédia centralisé</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Indique s’il existe un point de terminaison multimédia connu (par exemple, une passerelle RTC où le point de terminaison multimédia possède la même adresse IP que le point de terminaison de signalisation).</p></td>
</tr>
<tr class="even">
<td><p>Activer l’accrochage RTP</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indique si les jonctions SIP (Session Initiation Protocol) prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP par le biais d’un appareil ou d’un pare-feu NAT (Network Address Translator).</p></td>
</tr>
<tr class="odd">
<td><p>Activer l’historique du transfert d’appel</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.</p></td>
</tr>
<tr class="even">
<td><p>Activer les données de transfert P-Asserted-Identity</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>Activer le minuteur de basculement de routage de trafic sortant</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront routés vers la jonction suivante disponible. En l’absence d’autre jonction, l’appel est abandonné automatiquement. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</p></td>
</tr>
<tr class="even">
<td><p>Utilisations RTC associées</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Collection d’utilisations RTC affectées à la jonction.</p></td>
</tr>
<tr class="odd">
<td><p>Numéro converti à tester</p></td>
<td><p>S/O</p></td>
<td><p>Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.</p></td>
</tr>
<tr class="even">
<td><p>Règles de conversion associées</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Collection de règles de conversion de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels routés vers les destinations PBX ou RTC).</p></td>
</tr>
<tr class="odd">
<td><p>Règles de conversion du numéro appelé</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Collection de règles de conversion de numéro d’appel sortant affectées à la jonction.</p></td>
</tr>
<tr class="even">
<td><p>Numéro de téléphone à tester</p></td>
<td><p>S/O</p></td>
<td><p>Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de conversion.</p></td>
</tr>
<tr class="odd">
<td><p>Numéro appelant</p></td>
<td><p>S/O</p></td>
<td><p>Indique que le numéro de téléphone à tester est celui de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>Numéro appelé</p></td>
<td><p>S/O</p></td>
<td><p>Indique que le numéro de téléphone à tester est celui de la personne appelée.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Les applets de commande Lync Server CsTrunkConfiguration prennent en charge des propriétés supplémentaires qui ne figurent pas dans le panneau de configuration de Lync Server. Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">nouvelle-CsTrunkConfiguration</A> .



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Pour créer des paramètres de configuration de Trunk en utilisant le panneau de configuration de Lync Server

1.  Dans le panneau de configuration de Lync Server, cliquez sur **routage des communications vocales**, puis cliquez sur **configuration de Trunk**.

2.  Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.

3.  Dans la boîte de dialogue **Sélectionner un site** ou **Sélectionner un service** (la boîte de dialogue qui s’affiche change selon que vous créez des paramètres au niveau de l’étendue Site ou de l’étendue Service), sélectionnez l’emplacement des nouveaux paramètres de configuration, puis cliquez sur **OK**. Si la boîte de dialogue est vide, vous ne pouvez pas créer de paramètres supplémentaires. Par exemple, si la boîte de dialogue **Sélectionner un site** est vide, une collection de sites de configuration de jonctions a déjà été affectée à l’ensemble de vos sites et chaque site (chaque service) ne peut héberger qu’une seule collection de ce type. Dans ce cas, vous pouvez supprimer la collection existante et créer une autre collection ou modifier simplement la collection existante.

4.  Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.

5.  La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.

6.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.

7.  Dans la boîte de dialogue **panneau de configuration Microsoft Lync Server 2013** , cliquez sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

