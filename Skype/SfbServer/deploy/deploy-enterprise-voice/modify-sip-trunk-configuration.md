---
title: Modifier les paramètres de configuration jonction SIP dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 'Résumé : Découvrez comment modifier les paramètres de configuration de jonction SIP à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: 2a507b49318491528b025c3a8aba67e43a9dd82c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998167"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modifier les paramètres de configuration jonction SIP dans Skype pour Business Server
 
**Résumé :** Découvrez comment modifier les paramètres de configuration de jonction SIP à l’aide de la Skype pour le panneau de configuration serveur Business.
  
Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :
  
- si la déviation du trafic multimédia doit être activée sur les jonctions ;
    
- les conditions dans lesquelles les paquets RTCP sont envoyés ;
    
- si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.
    
Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Une de ces collections peut être modifiée ultérieurement à l’aide de deux Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell.
  
Lorsque vous modifiez les paramètres de configuration de jonction SIP à l’aide de Skype pour le panneau de configuration serveur Business, les options suivantes sont disponibles pour vous.
  
|**Paramètre de l’interface utilisateur**|**Paramètre PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identity  <br/> |Identificateur unique de la collection. Cette propriété est en lecture seule. Vous ne pouvez pas modifier l’identité d’une collection de paramètres de configuration des jonctions.  <br/> |
|Description  <br/> |Description  <br/> |Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).  <br/> |
|Nombre maximal de boîtes de dialogue préliminaires prises en charge  <br/> |MaxEarlyDialogs  <br/> |Nombre maximal de réponses dirigées qu’une passerelle RTC, un système IP-PBX ou un contrôleur de session en périphérie côté fournisseur de services peut recevoir à une invitation envoyée au serveur de médiation.  <br/> |
|Niveau de prise en charge du chiffrement  <br/> |SRTPMode  <br/> | Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle RTC, le système IP-PBX ou le contrôleur SBC (Session Border Controller) côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. Configuration multimédia est définie à l’aide des applets de commande [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) et [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) . <br/>  Les valeurs autorisées sont les suivantes : <br/>  Obligatoire : le chiffrement SRTP doit être utilisé. <br/>  Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge. <br/>  Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé. <br/>  SRTPMode n’est utilisé que si la passerelle est configurée de manière à utiliser le protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.<br/> |
|Prise en charge de la référence  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Si ce paramètre défini sur **Activer la référence d’appel vers la passerelle**, cela indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.  <br/> S’il est défini sur **Activer la référence avec un contrôle d’appel tiers**, cela indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé. Le protocole 3pcc est également appelé « contrôle tiers » et est employé quand un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel d’une personne A à une personne B).<br/> |
|Activer la déviation du trafic multimédia  <br/> |EnableBypass  <br/> |Indique si la déviation du trafic multimédia est activée pour cette jonction. La déviation du trafic multimédia ne peut être activée que si **Traitement multimédia centralisé** est activé également.<br/> |
|Traitement multimédia centralisé  <br/> |ConcentratedTopology  <br/> |Indique s’il existe un point de terminaison multimédia connu (par exemple, une passerelle RTC où le point de terminaison multimédia possède la même adresse IP que le point de terminaison de signalisation).  <br/> |
|Activer l’accrochage RTP  <br/> |EnableRTPLatching  <br/> |Indique si les jonctions SIP (Session Initiation Protocol) prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP par le biais d’un appareil ou d’un pare-feu NAT (Network Address Translator).  <br/> |
|Activer l’historique du transfert d’appel  <br/> |ForwardCallHistory  <br/> |Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.  <br/> |
|Activer les données de transfert P-Asserted-Identity  <br/> |ForwardPAI  <br/> |Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.  <br/> |
|Activer le minuteur de basculement de routage de trafic sortant  <br/> |EnableFastFailoverTimer  <br/> |Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront routés vers la jonction suivante disponible. En l’absence d’autre jonction, l’appel est abandonné automatiquement. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.  <br/> |
|Utilisations RTC associées  <br/> |PSTNUsages  <br/> |Collection d’utilisations RTC affectées à la jonction.  <br/> |
|Numéro converti à tester  <br/> |N/A  <br/> |Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.  <br/> |
|Règles de conversion associées  <br/> |OutboundTranslationRulesList  <br/> |Collection de règles de conversion de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels routés vers les destinations PBX ou RTC).  <br/> |
|Règles de conversion du numéro appelé  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Collection de règles de conversion de numéro d’appel sortant affectées à la jonction.  <br/> |
|Numéro de téléphone à tester  <br/> |N/A  <br/> |Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de conversion.  <br/> |
|Numéro appelant  <br/> |N/A  <br/> |Indique que le numéro de téléphone à tester est celui de l’appelant.  <br/> |
|Numéro appelé  <br/> |N/A  <br/> |Indique que le numéro de téléphone à tester est celui de la personne appelée.  <br/> |
   
> [!NOTE]
> Les applets de commande Lync Server CsTrunkConfiguration prend en charge les propriétés supplémentaires non affichées dans le panneau de configuration Lync Server. Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps) .
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour modifier les paramètres de configuration de jonction SIP à l’aide de Skype pour Business Server Control Panel

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales**, puis cliquez sur **Configuration de jonction**.
    
2. Sous l’onglet **Configuration de la jonction**, double-cliquez sur les paramètres de configuration de la jonction à modifier. Notez que vous ne pouvez modifier qu’une collection de paramètres à la fois. Si vous voulez apporter les mêmes modifications à plusieurs collections, utilisez Windows PowerShell à la place.
    
3. Dans la boîte de dialogue **Modifier la configuration de la jonction**, sélectionnez les éléments appropriées, puis cliquez sur **OK**.
    
4. La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.
    
5. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
    
6. Dans la boîte de dialogue **Skype pour Business Server le panneau de configuration** , cliquez sur **OK**.
    

