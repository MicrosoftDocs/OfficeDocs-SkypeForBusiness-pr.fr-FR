---
title: Modifier les paramètres de configuration jonction SIP dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. '
ms.openlocfilehash: a9c6bef538fd11b9e7d134fc1b952d81a8de1545
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896161"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modifier les paramètres de configuration jonction SIP dans Skype pour Business Server

Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. Ces paramètres spécifient, par exemple :

- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets Real-Time transport control protocol (RTCP) sont envoyés.
- Ou non sécurisé en temps réel (chiffrement SRTP protocol) est requis sur chaque jonction.

Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Une de ces collections peut être modifiée ultérieurement à l’aide de la soit Skype pour le panneau de configuration serveur Business ou Windows PowerShell.

Lorsque vous modifiez les paramètres de configuration de jonction SIP à l’aide de la Skype pour Business Server Server le panneau de configuration, les options suivantes sont disponibles :

|Paramètre de l’interface utilisateur |Paramètre PowerShell |Description |
|--|--|--|
|Nom|Identity|Identificateur unique de la collection. Cette propriété est en lecture seule. Vous ne pouvez pas modifier l’identité d’une collection de paramètres de configuration des jonctions.|
|Description|Description|Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).|
|Nombre maximal de boîtes de dialogue préliminaires prises en charge|MaxEarlyDialogs|Nombre maximal de réponses dirigées qu’une passerelle RTC, un système IP-PBX ou un contrôleur de session en périphérie côté fournisseur de services peut recevoir à une invitation envoyée au serveur de médiation.|
|Niveau de prise en charge du chiffrement|SRTPMode|Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle RTC, le système IP-PBX ou le contrôleur SBC (Session Border Controller) côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. Configuration multimédia est définie à l’aide des applets de commande New-CsMediaConfiguration et Set-CsMediaConfiguration.<br/>Les valeurs autorisées sont les suivantes :<br/><br/>**Requis**: le chiffrement SRTP doit être utilisé.<br/>**Facultatif**: le chiffrement SRTP sera utilisé si la passerelle prend en charge.<br/>**Non pris en charge**: le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.<br/><br/>SRTPMode n’est utilisé que si la passerelle est configurée de manière à utiliser le protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.|
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
|Numéro appelant|N/A|Indique que le numéro de téléphone à tester est celui de l’appelant.|
|Numéro appelé|N/A|Indique que le numéro de téléphone à tester est celui de la personne appelée.|
|||

> [!Note]
> Skype pour Business Server CsTrunkConfiguration applets de commande prend en charge les propriétés supplémentaires n’apparaît dans le Skype pour le panneau de configuration serveur Business. Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration) . 

**Pour modifier les paramètres de configuration de jonction SIP à l’aide de la Skype pour Business Server Control Panel**

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales**, puis cliquez sur **Configuration de jonction**.
2. Sous l’onglet **Configuration de la jonction**, double-cliquez sur les paramètres de configuration de la jonction à modifier. Notez que vous ne pouvez modifier qu’une collection de paramètres à la fois. Si vous voulez apporter les mêmes modifications à plusieurs collections, utilisez Windows PowerShell à la place.
3. Dans la boîte de dialogue **Modifier la Configuration de jonction** , effectuez les sélections appropriées, puis cliquez sur **OK**.
4. La propriété État de la collection est définie sur la valeur Non validé. Pour valider les modifications et à supprimer de la collection, cliquez sur **Valider**, puis cliquez sur **Valider tout**.
5. Dans la boîte de dialogue **Paramètre de Configuration de voix non validés**, cliquez sur **OK**.
6. Dans la boîte de dialogue **Skype pour Business Server le panneau de configuration** , cliquez sur **OK**.
