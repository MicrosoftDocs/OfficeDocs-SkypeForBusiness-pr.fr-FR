---
title: 'Skype Entreprise Server : créer une collection de paramètres de configuration de la trunk'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Les paramètres de configuration de la liaison de session SIP définissent la relation entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un PBX IP ou un contrôleur SBC (Session Border Controller) chez le fournisseur de services.
ms.openlocfilehash: 863123c21db831146a03de946992a1eb7ed06840
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763552"
---
# <a name="skype-for-business-server-create-a-new-collection-of-trunk-configuration-settings"></a>Skype Entreprise Server : créer une collection de paramètres de configuration de la trunk

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :
- L’activation ou non du contournement de média sur les jonctions.
- Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).
- L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

Lorsque vous créez des paramètres de configuration de trunk SIP à l’aide du Panneau de configurationSkype for Business Server, les options suivantes sont disponibles :

|Paramètre de l’interface utilisateur | Paramètre PowerShell | Description |
|--|--|--|
|Nom|Identité|Identificateur unique de la collection. Cette propriété est en lecture seule ; vous ne pouvez pas changer l’identité d’une collection de paramètres de configuration de jonctions.|
|Description|Description|Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).|
|Nombre maximal de boîtes de dialogue préliminaires prises en charge|MaxEarlyDialogs|Nombre maximal de réponses dirigées qu’une passerelle PSTN, un système IP-PBX ou un contrôleur de session en périphérie du côté fournisseur de services peut recevoir à une invitation qui est envoyée au serveur de médiation.|
|Niveau de prise en charge du chiffrement|SRTPMode|Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle PSTN, le système IP-PBX ou le contrôleur de session en périphérie du côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. La configuration multimédia est définie à l’aide des cmdlets [New-CsMediaConfiguration](/powershell/module/skype/New-CsMediaConfiguration) et [Set-CsMediaConfiguration.](/powershell/module/skype/Set-CsMediaConfiguration)<br/>Les valeurs autorisées sont les suivantes :<br/><br/>**Obligatoire**: le chiffrement SRTP doit être utilisé.<br/>**Facultatif**: SRTP sera utilisé si la passerelle la prend en charge.<br/>**Non pris en** charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.<br/><br/>SRTPMode est utilisé uniquement si la passerelle est configurée en vue d’un recours au protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.|
|Prise en charge de la référence|Enable3pccRefer<br/>EnableReferSupport|Si défini sur **Activer la référence d’appel vers la passerelle**, indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.<br/>Si défini sur **Activer la référence avec un contrôle d’appel tiers**, indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé. 3pcc est également connu sous le nom de « contrôle tiers », et se produit quand un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel d’une personne A à une personne B).|
|Activer le contournement de média|EnableBypass|Indique si le contournement de média est activé pour cette jonction. Le contournement de média peut être activé uniquement si **Traitement multimédia centralisé** est également activé.|
|Traitement multimédia centralisé|ConcentratedTopology|Indique si une terminaison multimédia connue existe (par exemple, une passerelle PSTN où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation).|
|Activer l’accrochage RTP|EnableRTPLatching|Indique si les jonctions SIP prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP via un appareil ou un pare-feu NAT (traduction d’adresses réseau).|
|Activer l’historique du transfert d’appel|ForwardCallHistory|Indique si les informations d’historique d’appel sont transférées via la jonction.|
|Activer les données de transfert P-Asserted-Identity|ForwardPAI|Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.|
|Activer le minuteur de basculement de routage de trafic sortant|EnableFastFailoverTimer|Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront acheminés vers la jonction suivante disponible ; s’il n’existe aucune jonction supplémentaire, l’appel est automatiquement abandonné. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.|
|Utilisations PSTN associées|PSTNUsages|Collection d’utilisations PSTN assignées à la jonction.|
|Numéro traduit à tester|N/A|Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.|
|Règles de traduction associées|OutboundTranslationRulesList|Collection de règles de traduction de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels acheminés vers les destinations PBX ou PSTN).|
|Règles de traduction du numéro appelé|OutboundCallingNumberTranslationRulesList|Collection de règles de traduction de numéro d’appel sortant assignées à la jonction.|
|Numéro de téléphone à tester|N/A|Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de traduction.|
|Numéro appelant|N/A|Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de traduction.|
|Numéro appelé|N/A|Indique que le numéro de téléphone à tester est celui de la personne appelée.|
||||

> [!Note]
> Les Skype Entreprise Server cmdlets CsTrunkConfiguration peuvent prendre en charge des propriétés supplémentaires qui ne sont pas affichées Skype Entreprise Server panneau de configuration. Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [New-CsTrunkConfiguration.](/powershell/module/skype/New-CsTrunkConfiguration) 

**Pour créer de nouveaux paramètres de configuration de la Skype Entreprise Server panneau de configuration**

1. Dans le Skype Entreprise Server de configuration, cliquez sur **Routage** des voix, puis sur **Configuration de la trunk .**
2. Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site, ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.
3. Dans la boîte de dialogue Sélectionner un **site** ou Sélectionner un **service** (la boîte de dialogue qui s’affiche varie selon que vous créez des paramètres d’étendue site ou de service), sélectionnez l’emplacement des nouveaux paramètres de configuration, puis cliquez sur **OK.** Si la boîte de dialogue est vide, cela signifie qu’il n’y a aucun endroit pour créer les nouveaux paramètres ; Par exemple,  si la boîte de dialogue Sélectionner un site est vide, cela signifie que tous vos sites ont déjà été affectés à une collection de sites de configuration de trunk, et que chaque site (et chaque service) ne peut héberger qu’une seule collection de ce type. Dans ce cas, vous pouvez supprimer la collection existante et créer une nouvelle collection, ou simplement modifier la collection existante.
4. Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.
5. La propriété **État** de la collection aura la valeur **Non validé**. Pour valider les modifications et pour supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.
6. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
7. Dans la **boîte Skype Entreprise panneau de bord,** cliquez sur **OK.**
