---
title: Créer une collection de paramètres de configuration de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: 'Résumé : Découvrez comment créer une collection de paramètres de configuration de Skype Entreprise Server panneau de configuration.'
ms.openlocfilehash: 2a6db1b82693ce78bd48ff8cc816503026871a09
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856291"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Créer une collection de paramètres de configuration de Skype Entreprise Server

**Résumé :** Découvrez comment créer une collection de paramètres de configuration de la Skype Entreprise Server panneau de configuration.
  
Les paramètres de configuration de la trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un PBX (IP-Public Branch eXchange) ou un contrôleur SBC (Session Border Controller) chez le fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :
  
- L’activation ou non du contournement de média sur les jonctions.
    
- Conditions dans lesquelles les paquets RTCP (Realtime Transport Control Protocol) sont envoyés.
    
- Si le chiffrement SRTP (Secure Realtime Transport Protocol) est requis sur chaque trunk.
    
Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).
  
Lorsque vous créez des paramètres de configuration de Skype Entreprise Server sip à l’aide du Panneau de configuration, les options suivantes sont disponibles.
  
|**Paramètre de l’interface utilisateur**|**Paramètre PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identité  <br/> |Identificateur unique de la collection. Cette propriété est en lecture seule ; vous ne pouvez pas changer l’identité d’une collection de paramètres de configuration de jonctions.  <br/> |
|Description  <br/> |Description  <br/> |Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).  <br/> |
|Nombre maximal de boîtes de dialogue préliminaires prises en charge  <br/> |MaxEarlyDialogs  <br/> |Nombre maximal de réponses dirigées qu’une passerelle PSTN, un système IP-PBX ou un contrôleur de session en périphérie du côté fournisseur de services peut recevoir à une invitation qui est envoyée au serveur de médiation.  <br/> |
|Niveau de prise en charge du chiffrement  <br/> |SRTPMode  <br/> | Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle PSTN, le système IP-PBX ou le contrôleur de session en périphérie du côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. La configuration multimédia est définie à l’aide des cmdlets [New-CsMediaConfiguration](/powershell/module/skype/new-csmediaconfiguration) et [Set-CsMediaConfiguration.](/powershell/module/skype/set-csmediaconfiguration) <br/>  Les valeurs autorisées sont les suivantes : <br/>  Requis : le chiffrement SRTP doit être utilisé. <br/>  Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge. <br/>  Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé. <br/>  SRTPMode est utilisé uniquement si la passerelle est configurée en vue d’un recours au protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.<br/> |
|Prise en charge de la référence  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Si défini sur **Activer la référence d’appel vers la passerelle**, indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.  <br/> Si défini sur **Activer la référence avec un contrôle d’appel tiers**, indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé. 3pcc est également connu sous le nom de « contrôle tiers », et se produit quand un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel d’une personne A à une personne B).<br/> |
|Activer le contournement de média  <br/> |EnableBypass  <br/> |Indique si le contournement de média est activé pour cette jonction. Le contournement de média peut être activé uniquement si **Traitement multimédia centralisé** est également activé.<br/> |
|Traitement multimédia centralisé  <br/> |ConcentratedTopology  <br/> |Indique si une terminaison multimédia connue existe (par exemple, une passerelle PSTN où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation).  <br/> |
|Activer l’accrochage RTP  <br/> |EnableRTPLatching  <br/> |Indique si les jonctions SIP prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP via un appareil ou un pare-feu NAT (traduction d’adresses réseau).  <br/> |
|Activer l’historique du transfert d’appel  <br/> |ForwardCallHistory  <br/> |Indique si les informations d’historique d’appel sont transférées via la jonction.  <br/> |
|Activer les données de transfert P-Asserted-Identity  <br/> |ForwardPAI  <br/> |Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.  <br/> |
|Activer le minuteur de basculement de routage de trafic sortant  <br/> |EnableFastFailoverTimer  <br/> |Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront acheminés vers la jonction suivante disponible ; s’il n’existe aucune jonction supplémentaire, l’appel est automatiquement abandonné. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.  <br/> |
|Utilisations PSTN associées  <br/> |PSTNUsages  <br/> |Collection d’utilisations PSTN assignées à la jonction.  <br/> |
|Numéro traduit à tester  <br/> |S/O  <br/> |Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.  <br/> |
|Règles de traduction associées  <br/> |OutboundTranslationRulesList  <br/> |Collection de règles de traduction de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels acheminés vers les destinations PBX ou PSTN).  <br/> |
|Règles de traduction du numéro appelé  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Collection de règles de traduction de numéro d’appel sortant assignées à la jonction.  <br/> |
|Numéro de téléphone à tester  <br/> |S/O  <br/> |Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de traduction.  <br/> |
|Numéro appelant  <br/> |S/O  <br/> |Indique que le numéro de téléphone à tester est celui de l’appelant.  <br/> |
|Numéro appelé  <br/> |S/O  <br/> |Indique que le numéro de téléphone à tester est celui de la personne appelée.  <br/> |
   
> [!NOTE]
> Les Skype Entreprise Server cmdlets CsTrunkConfiguration peuvent prendre en charge des propriétés supplémentaires qui ne sont pas affichées Skype Entreprise Server panneau de configuration. Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [New-CsTrunkConfiguration.](/powershell/module/skype/new-cstrunkconfiguration)
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour créer de nouveaux paramètres de configuration de la Skype Entreprise Server panneau de configuration

1. Dans Skype Entreprise Server panneau de configuration, cliquez **sur Routage** des voix, puis sur **Configuration de la trunk .**
    
2. Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site, ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.
    
3. Dans la boîte de dialogue **Sélectionner un site** ou **Sélectionner un service** (la boîte de dialogue qui s’affiche change selon que vous créez des paramètres au niveau de l’étendue Site ou au niveau de l’étendue Service), sélectionnez l’emplacement des nouveaux paramètres de configuration, puis cliquez sur **OK**. Si la boîte de dialogue est vide, cela signifie que vous ne pouvez pas créer de paramètres supplémentaires. Par exemple, si la boîte de dialogue **Sélectionner un site** est vide, cela signifie qu’une collection de sites de configuration de jonctions a déjà été affectée à l’ensemble de vos sites et que chaque site (chaque service) ne peut héberger qu’une seule collection de ce type. Dans ce cas, vous pouvez soit supprimer la collection existante et créer une autre collection, soit modifier simplement la collection existante.
    
4. Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.
    
5. La propriété **État** de la collection aura la valeur **Non validé**. Pour valider les modifications et pour supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.
    
6. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
    
7. Dans la **boîte Skype Entreprise Server de dialogue Panneau de** Skype Entreprise Server cliquez sur **OK.**
