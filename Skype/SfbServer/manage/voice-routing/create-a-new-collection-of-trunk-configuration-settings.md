---
title: Créer une nouvelle collection de jonction paramètres de configuration dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service.
ms.openlocfilehash: 86a731c07f3c7289e5eabcd74bb3ccf37ec4df9d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890450"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Créer une nouvelle collection de jonction paramètres de configuration dans Skype pour Business Server

Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. Ces paramètres spécifient, par exemple :
- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets Real-Time transport control protocol (RTCP) sont envoyés.
- Ou non sécurisé en temps réel (chiffrement SRTP protocol) est requis sur chaque jonction.

Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

Lorsque vous créez usingSkype de paramètres de configuration de jonction SIP pour le panneau de configuration serveur Business, les options suivantes sont disponibles :

|Paramètre de l’interface utilisateur | Paramètre PowerShell | Description |
|--|--|--|
|Nom|Identity|Identificateur unique de la collection. Cette propriété est en lecture seule. Vous ne pouvez pas modifier l’identité d’une collection de paramètres de configuration des jonctions.|
|Description|Description|Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).|
|Nombre maximal de boîtes de dialogue préliminaires prises en charge|MaxEarlyDialogs|Nombre maximal de réponses dirigées qu’une passerelle RTC, un système IP-PBX ou un contrôleur de session en périphérie côté fournisseur de services peut recevoir à une invitation envoyée au serveur de médiation.|
|Niveau de prise en charge du chiffrement|SRTPMode|Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle RTC, le système IP-PBX ou le contrôleur SBC (Session Border Controller) côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. Configuration multimédia est définie à l’aide des applets de commande [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) et [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) .<br/>Les valeurs autorisées sont les suivantes :<br/><br/>**Requis**: le chiffrement SRTP doit être utilisé.<br/>**Facultatif**: le chiffrement SRTP sera utilisé si la passerelle prend en charge.<br/>**Non pris en charge**: le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.<br/><br/>SRTPMode n’est utilisé que si la passerelle est configurée de manière à utiliser le protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.|
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
> Skype pour Business Server CsTrunkConfiguration applets de commande prend en charge les propriétés supplémentaires non affichées dans Skype pour le panneau de configuration serveur Business. Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) . 

**Pour créer des paramètres de configuration de nouvelle jonction à l’aide de Skype pour Business Server Control Panel**

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales**, puis cliquez sur **Configuration de jonction**.
2. Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.
3. Dans la **sélection d’un Site** ou la boîte de dialogue **Sélectionner un Service** (la boîte de dialogue qui s’affiche dépend de si vous créez des paramètres étendus à un site ou service étendue), sélectionnez l’emplacement pour les nouveaux paramètres de configuration, puis sur **OK **. Si la boîte de dialogue est vide, ce qui signifie qu’il n’existe pas de place pour créer les nouveaux paramètres ; par exemple, si la boîte de dialogue **Sélectionner un Site** est vide, cela signifie que tous vos sites ont déjà affectés à une collection de sites de configuration de jonction, et chaque site (et chaque service) peuvent héberger uniquement une collection de ce type. Dans ce cas, vous pouvez soit supprimer la collection existante et créer une nouvelle collection ou simplement modifier la collection existante.
4. Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.
5. La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.
6. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
7. Dans la boîte de dialogue **Skype pour Business le panneau de configuration** , cliquez sur **OK**.
