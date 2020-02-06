---
title: Créer une collection de paramètres de configuration de Trunk dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services.
ms.openlocfilehash: 6db4978151bf9b649375adb7a2200710a1a503c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817004"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Créer une collection de paramètres de configuration de Trunk dans Skype entreprise Server

Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. Ces paramètres spécifient, par exemple :
- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.
- Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.

Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

Les options suivantes sont disponibles lors de la création de paramètres de configuration du Trunk SIP Utilisezskype pour le panneau de configuration pour les entreprises :

|Paramètre de l’interface utilisateur | Paramètre PowerShell | Description |
|--|--|--|
|Nom|Identity|Identificateur unique de la collection. Cette propriété est en lecture seule. Vous ne pouvez pas modifier l’identité d’une collection de paramètres de configuration des jonctions.|
|Description|Description|Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).|
|Nombre maximal de boîtes de dialogue préliminaires prises en charge|MaxEarlyDialogs|Nombre maximal de réponses dirigées qu’une passerelle RTC, un système IP-PBX ou un contrôleur de session en périphérie côté fournisseur de services peut recevoir à une invitation envoyée au serveur de médiation.|
|Niveau de prise en charge du chiffrement|SRTPMode|Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle RTC, le système IP-PBX ou le contrôleur SBC (Session Border Controller) côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. La configuration de média est définie à l’aide de la cmdlet [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) et de [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) .<br/>Les valeurs autorisées sont les suivantes :<br/><br/>**Obligatoire**: le chiffrement SRTP doit être utilisé.<br/>**Facultatif**: SRTP est utilisé si la passerelle le prend en charge.<br/>**Non pris en charge**: le chiffrement SRTP n’est pas pris en charge et n’est donc pas utilisé.<br/><br/>SRTPMode n’est utilisé que si la passerelle est configurée de manière à utiliser le protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.|
|Prise en charge de la référence|Enable3pccRefer<br/>EnableReferSupport|Si ce paramètre défini sur **Activer la référence d’appel vers la passerelle**, cela indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.<br/>S’il est défini sur **Activer la référence avec un contrôle d’appel tiers**, cela indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé. Le protocole 3pcc est également appelé « contrôle tiers » et est employé quand un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel d’une personne A à une personne B).|
|Activer la déviation du trafic multimédia|EnableBypass|Indique si la déviation du trafic multimédia est activée pour cette jonction. La déviation du trafic multimédia ne peut être activée que si **Traitement multimédia centralisé** est activé également.|
|Traitement multimédia centralisé|ConcentratedTopology|Indique s’il existe un point de terminaison multimédia connu (par exemple, une passerelle RTC où le point de terminaison multimédia possède la même adresse IP que le point de terminaison de signalisation).|
|Activer l’accrochage RTP|EnableRTPLatching|Indique si les jonctions SIP (Session Initiation Protocol) prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP par le biais d’un appareil ou d’un pare-feu NAT (Network Address Translator).|
|Activer l’historique du transfert d’appel|ForwardCallHistory|Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.|
|Activer les données de transfert P-Asserted-Identity|ForwardPAI|Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.|
|Activer le minuteur de basculement de routage de trafic sortant|EnableFastFailoverTimer|Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront routés vers la jonction suivante disponible. En l’absence d’autre jonction, l’appel est abandonné automatiquement. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.|
|Utilisations RTC associées|PSTNUsages|Collection d’utilisations RTC affectées à la jonction.|
|Numéro converti à tester|N/A|Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.|
|Règles de conversion associées|OutboundTranslationRulesList|Collection de règles de conversion de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels routés vers les destinations PBX ou RTC).|
|Règles de conversion du numéro appelé|OutboundCallingNumberTranslationRulesList|Collection de règles de conversion de numéro d’appel sortant affectées à la jonction.|
|Numéro de téléphone à tester|N/A|Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de conversion.|
|Numéro appelant|N/A|Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de conversion.|
|Numéro appelé|N/A|Indique que le numéro de téléphone à tester est celui de la personne appelée.|
||||

> [!Note]
> Les applets de commande Skype entreprise Server CsTrunkConfiguration prennent en charge des propriétés supplémentaires qui ne sont pas affichées dans le panneau de configuration Skype entreprise Server. Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) . 

**Pour créer des paramètres de configuration de Trunk en utilisant le panneau de configuration Skype entreprise Server**

1. Dans le panneau de configuration Skype entreprise Server, cliquez sur **routage des communications vocales**, puis cliquez sur **configuration de Trunk**.
2. Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.
3. Dans la boîte de dialogue **Sélectionner un site** ou **Sélectionner un service** (la boîte de dialogue qui s’affiche varie selon que vous créez des paramètres d’étendue de sites ou de service), sélectionnez l’emplacement des nouveaux paramètres de configuration, puis cliquez sur **OK**. Si la boîte de dialogue est vide, cela signifie qu’il n’y a aucun emplacement pour créer les nouveaux paramètres. par exemple, si la boîte de dialogue **Sélectionner un site** est vide, cela signifie que tous vos sites possèdent déjà une collection de sites de configuration de Trunk et chaque site (et chaque service) peut uniquement héberger une telle collection. Dans ce cas, vous pouvez supprimer la collection existante et créer une nouvelle collection, ou simplement modifier la collection existante.
4. Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.
5. La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.
6. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
7. Dans la boîte de dialogue **panneau de configuration Skype pour les entreprises** , cliquez sur **OK**.
