---
title: "Modif. des paramètres de conf. d’une jonction SIP dans Lync Server 2013"
TOCtitle: "Modif. des paramètres de conf. d’une jonction SIP dans Lync Server 2013"
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49891408
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification des paramètres de configuration d’une jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les paramètres de configuration de jonctions SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

  - L’activation ou non du contournement de média sur les jonctions.

  - Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).

  - L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Quand vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP est automatiquement créée. De plus, les administrateurs peuvent créer des collections de paramètres personnalisés au niveau du site ou du service (pour le service de passerelle PSTN uniquement). Ces collections peuvent être modifiées ultérieurement dans le Panneau de configuration Lync Server ou Windows PowerShell.

Quand vous modifiez les paramètres de configuration de jonction SIP avec le Panneau de configuration Lync Server, les options suivantes sont disponibles :


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
<td><p>Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle PSTN, le système IP-PBX ou le contrôleur de session en périphérie du côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. La définition de la configuration multimédia s’effectue à l’aide des applets de commande <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a>.</p>
<p>Les valeurs autorisées sont les suivantes :</p><ul><li><p>Requis : le chiffrement SRTP doit être utilisé.</p></li><li><p>Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge.</p></li><li><p>Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.</p></li></ul>
<p>SRTPMode est utilisé uniquement si la passerelle est configurée en vue d’un recours au protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.</p></td>
</tr>
<tr class="odd">
<td><p>Prise en charge de la référence</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Si défini sur <strong>Activer la référence d’appel vers la passerelle</strong>, indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.</p>
<p>Si défini sur <strong>Activer la référence avec un contrôle d’appel tiers</strong>, indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé. 3pcc est également connu sous le nom de « contrôle tiers », et se produit quand un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel d’une personne A à une personne B).</p></td>
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
<td><p>N/A</p></td>
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
<td><p>N/A</p></td>
<td><p>Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de traduction.</p></td>
</tr>
<tr class="odd">
<td><p>Numéro appelant</p></td>
<td><p>N/A</p></td>
<td><p>Indique que le numéro de téléphone à tester est celui de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>Numéro appelé</p></td>
<td><p>N/A</p></td>
<td><p>Indique que le numéro de téléphone à tester est celui de la personne appelée.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Les applets de commande CsTrunkConfiguration de Lync Server prennent en charge d’autres propriétés qui ne sont pas affichées dans le Panneau de configuration Lync Server. Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</a>.

## Modification des paramètres de configuration de jonction SIP avec le Panneau de configuration Lync Server

1.  Dans le Panneau de configuration Lync Server, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

2.  Sous l’onglet **Configuration de la jonction**, double-cliquez sur les paramètres de configuration de la jonction à modifier. Notez que vous ne pouvez modifier qu’une collection de paramètres à la fois. Si vous voulez apporter les mêmes modifications à plusieurs collections, utilisez Windows PowerShell à la place.

3.  Dans la boîte de dialogue **Modifier la configuration de la jonction**, sélectionnez les éléments souhaités, puis cliquez sur **OK**.

4.  La propriété **État** de la collection aura la valeur **Non validé**. Pour valider les modifications et pour supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.

5.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.

6.  Dans la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013**, cliquez sur **OK**.

