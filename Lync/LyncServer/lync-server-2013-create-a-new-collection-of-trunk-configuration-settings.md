---
title: 'Lync Server 2013 : créer une collection de paramètres de configuration de jonction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f988b096b6f991cb52b4d1238219b67364c37ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>Créer une collection de paramètres de configuration de jonction dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

  - L’activation ou non du contournement de média sur les jonctions.

  - Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).

  - L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP (Session Initiation Protocol) est créée. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

Lors de la création de paramètres de configuration de jonction SIP à l’aide du panneau de configuration Lync Server, les options suivantes sont disponibles :


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
<td><p>Identité</p></td>
<td><p>Identificateur unique de la collection. Cette propriété est en lecture seule ; vous ne pouvez pas changer l’identité d’une collection de paramètres de configuration de jonctions.</p></td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>Description</p></td>
<td><p>Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).</p></td>
</tr>
<tr class="odd">
<td><p>Nombre maximal de boîtes de dialogue préliminaires prises en charge</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Nombre maximal de réponses dirigées qu’une passerelle PSTN, un système IP-PBX ou un contrôleur de session en périphérie du côté fournisseur de services peut recevoir à une invitation qui est envoyée au serveur de médiation.</p></td>
</tr>
<tr class="even">
<td><p>Niveau de prise en charge du chiffrement</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle PSTN, le système IP-PBX ou le contrôleur de session en périphérie du côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. La configuration du média est définie à l’aide des cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> et <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</p>
<p>Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>Requis : le chiffrement SRTP doit être utilisé.</p></li>
<li><p>Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge.</p></li>
<li><p>Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.</p></li>
</ul>
<p>SRTPMode est utilisé uniquement si la passerelle est configurée en vue d’un recours au protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.</p></td>
</tr>
<tr class="odd">
<td><p>Prise en charge de la référence</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Si défini sur <strong>Activer la référence d’appel vers la passerelle</strong>, indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.</p>
<p>Si défini sur <strong>Activer la référence avec un contrôle d’appel tiers</strong>, indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé. 3PCC est également appelé contrôle &quot;tiers&quot; et se produit lorsqu’un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel de la personne a à la personne B).</p></td>
</tr>
<tr class="even">
<td><p>Activer le contournement de média</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indique si le contournement de média est activé pour cette jonction. Le contournement de média peut être activé uniquement si <strong>Traitement multimédia centralisé</strong> est également activé.</p></td>
</tr>
<tr class="odd">
<td><p>Traitement multimédia centralisé</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Indique si une terminaison multimédia connue existe (par exemple, une passerelle PSTN où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation).</p></td>
</tr>
<tr class="even">
<td><p>Activer l’accrochage RTP</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indique si les jonctions SIP prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP via un appareil ou un pare-feu NAT (traduction d’adresses réseau).</p></td>
</tr>
<tr class="odd">
<td><p>Activer l’historique du transfert d’appel</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indique si les informations d’historique d’appel sont transférées via la jonction.</p></td>
</tr>
<tr class="even">
<td><p>Activer les données de transfert P-Asserted-Identity</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>Activer le minuteur de basculement de routage de trafic sortant</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront acheminés vers la jonction suivante disponible ; s’il n’existe aucune jonction supplémentaire, l’appel est automatiquement abandonné. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</p></td>
</tr>
<tr class="even">
<td><p>Utilisations PSTN associées</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Collection d’utilisations PSTN assignées à la jonction.</p></td>
</tr>
<tr class="odd">
<td><p>Numéro traduit à tester</p></td>
<td><p>S/O</p></td>
<td><p>Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.</p></td>
</tr>
<tr class="even">
<td><p>Règles de traduction associées</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Collection de règles de traduction de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels acheminés vers les destinations PBX ou PSTN).</p></td>
</tr>
<tr class="odd">
<td><p>Règles de traduction du numéro appelé</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Collection de règles de traduction de numéro d’appel sortant assignées à la jonction.</p></td>
</tr>
<tr class="even">
<td><p>Numéro de téléphone à tester</p></td>
<td><p>S/O</p></td>
<td><p>Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de traduction.</p></td>
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
> Les applets de commande Lync Server applet cstrunkconfiguration prennent en charge les propriétés supplémentaires qui ne figurent pas dans le panneau de configuration Lync Server. Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-applet cstrunkconfiguration</A> .



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Pour créer de nouveaux paramètres de configuration de jonction à l’aide du panneau de configuration Lync Server

1.  Dans le panneau de configuration Lync Server, cliquez sur **routage des communications vocales**, puis sur Configuration de la **jonction**.

2.  Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site, ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.

3.  Dans la boîte de dialogue **Sélectionner un site** ou **Sélectionner un service** (la boîte de dialogue qui s’affiche change selon que vous créez des paramètres au niveau de l’étendue Site ou au niveau de l’étendue Service), sélectionnez l’emplacement des nouveaux paramètres de configuration, puis cliquez sur **OK**. Si la boîte de dialogue est vide, cela signifie que vous ne pouvez pas créer de paramètres supplémentaires. Par exemple, si la boîte de dialogue **Sélectionner un site** est vide, cela signifie qu’une collection de sites de configuration de jonctions a déjà été affectée à l’ensemble de vos sites et que chaque site (chaque service) ne peut héberger qu’une seule collection de ce type. Dans ce cas, vous pouvez soit supprimer la collection existante et créer une autre collection, soit modifier simplement la collection existante.

4.  Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.

5.  La propriété **État** de la collection aura la valeur **Non validé**. Pour valider les modifications et pour supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.

6.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.

7.  Dans la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013**, cliquez sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

