---
title: Création d’une collection de paramètres de configuration de jonction dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: 'Résumé : Apprenez à créer des paramètres de configuration une nouvelle collection de jonction à l’aide de la Skype pour le panneau de configuration de Business Server.'
ms.openlocfilehash: 9f62ac5dffd2eb6e84fd5efbcfbc4bd99cb7f092
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server-2015"></a>Création d’une collection de paramètres de configuration de jonction dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à créer des paramètres de configuration une nouvelle collection de jonction à l’aide de la Skype pour le panneau de configuration de Business Server.
  
Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :
  
- si la déviation du trafic multimédia doit être activée sur les jonctions ;
    
- les conditions dans lesquelles les paquets RTCP sont envoyés ;
    
- si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.
    
Lorsque vous installez Skype pour Business Server, une collection globale des paramètres de configuration SIP trunk est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).
  
Lors de la création de paramètres de configuration SIP trunk à l’aide de Skype pour Business Server du Panneau de configuration, les options suivantes sont disponibles pour vous.
  
|**Définition de l’interface utilisateur**|**Paramètre de PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identity  <br/> |Identificateur unique de la collection. Cette propriété est en lecture seule. Vous ne pouvez pas modifier l’identité d’une collection de paramètres de configuration des jonctions.  <br/> |
|Description  <br/> |Description  <br/> |Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).  <br/> |
|Nombre maximal de boîtes de dialogue préliminaires prises en charge  <br/> |MaxEarlyDialogs  <br/> |Nombre maximal de réponses dirigées qu’une passerelle RTC, un système IP-PBX ou un contrôleur de session en périphérie côté fournisseur de services peut recevoir à une invitation envoyée au serveur de médiation.  <br/> |
|Niveau de prise en charge du chiffrement  <br/> |SRTPMode  <br/> | Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle RTC, le système IP-PBX ou le contrôleur SBC (Session Border Controller) côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. Configuration de Media est définie à l’aide des applets de commande [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) et [CsMediaConfiguration de l’ensemble](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) . <br/>  Les valeurs autorisées sont les suivantes : <br/>  Obligatoire : le chiffrement SRTP doit être utilisé. <br/>  Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge. <br/>  Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé. <br/>  SRTPMode n’est utilisé que si la passerelle est configurée de manière à utiliser le protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.<br/> |
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
> Le Skype pour les applets de commande de CsTrunkConfiguration de serveur d’entreprise prennent en charge les propriétés supplémentaires non indiquées dans Skype pour le panneau de configuration de Business Server. Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cstrunkconfiguration?view=skype-ps) .
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour créer des paramètres de configuration nouveau trunk à l’aide de Skype pour le panneau de configuration de Business Server

1. Dans Skype pour le panneau de configuration de Business Server, cliquez sur **Routage des communications vocales**, puis cliquez sur **Configuration de jonction**.
    
2. Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.
    
3. Dans la boîte de dialogue **Sélectionner un site** ou **Sélectionner un service** (la boîte de dialogue qui s’affiche change selon que vous créez des paramètres au niveau de l’étendue Site ou de l’étendue Service), sélectionnez l’emplacement des nouveaux paramètres de configuration, puis cliquez sur **OK**. Si la boîte de dialogue est vide, vous ne pouvez pas créer de paramètres supplémentaires. Par exemple, si la boîte de dialogue **Sélectionner un site** est vide, une collection de sites de configuration de jonctions a déjà été affectée à l’ensemble de vos sites et chaque site (chaque service) ne peut héberger qu’une seule collection de ce type. Dans ce cas, vous pouvez supprimer la collection existante et créer une autre collection ou modifier simplement la collection existante.
    
4. Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.
    
5. La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.
    
6. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
    
7. Dans la boîte de dialogue **Skype pour le panneau de configuration de Business Server** , cliquez sur **OK**.
    

