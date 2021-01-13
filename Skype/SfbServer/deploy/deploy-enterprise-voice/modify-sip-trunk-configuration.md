---
title: Modifier les paramètres de configuration de la trunk SIP dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 'Résumé : Découvrez comment modifier les paramètres de configuration des trunks SIP à l’aide du Panneau de configuration de Skype Entreprise Server.'
ms.openlocfilehash: 43d32e04716423578173d7eed412445f196f9b65
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830774"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modifier les paramètres de configuration de la trunk SIP dans Skype Entreprise Server
 
**Résumé :** Découvrez comment modifier les paramètres de configuration des trunks SIP à l’aide du Panneau de configuration de Skype Entreprise Server.
  
Les paramètres de configuration de la liaison de session SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un PBX (IP-Public Branch eXchange) ou un contrôleur SBC (Session Border Controller) chez le fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :
  
- L’activation ou non du contournement de média sur les jonctions.
    
- Conditions dans lesquelles les paquets RTCP (Realtime Transport Control Protocol) sont envoyés.
    
- Si le chiffrement SRTP (Secure Realtime Transport Protocol) est requis sur chaque trunk.
    
Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Ces collections peuvent être modifiées ultérieurement à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
Lorsque vous modifiez les paramètres de configuration d’une trunk SIP à l’aide du Panneau de configuration de Skype Entreprise Server, les options suivantes sont disponibles.
  
|**Paramètre de l’interface utilisateur**|**Paramètre PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identité  <br/> |Identificateur unique de la collection. Cette propriété est en lecture seule ; vous ne pouvez pas changer l’identité d’une collection de paramètres de configuration de jonctions.  <br/> |
|Description  <br/> |Description  <br/> |Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).  <br/> |
|Nombre maximal de boîtes de dialogue préliminaires prises en charge  <br/> |MaxEarlyDialogs  <br/> |Nombre maximal de réponses dirigées qu’une passerelle PSTN, un système IP-PBX ou un contrôleur de session en périphérie du côté fournisseur de services peut recevoir à une invitation qui est envoyée au serveur de médiation.  <br/> |
|Niveau de prise en charge du chiffrement  <br/> |SRTPMode  <br/> | Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle PSTN, le système IP-PBX ou le contrôleur de session en périphérie du côté fournisseur de services. Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia. La configuration multimédia est définie à l’aide des cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) et [Set-CsMediaConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) <br/>  Les valeurs autorisées sont les suivantes : <br/>  Requis : le chiffrement SRTP doit être utilisé. <br/>  Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge. <br/>  Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé. <br/>  SRTPMode est utilisé uniquement si la passerelle est configurée en vue d’un recours au protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.<br/> |
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
> Les cmdlets CsTrunkConfiguration Lync Server prendre en charge des propriétés supplémentaires qui ne sont pas affichées dans le Panneau de configuration Lync Server. Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Set-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps)
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour modifier les paramètres de configuration des trunks SIP à l’aide du Panneau de configuration de Skype Entreprise Server

1. Dans le Panneau de configuration de Skype Entreprise Server, cliquez **sur Routage** des voix, puis sur **Configuration de la configuration de la configuration de la boîte aux formes.**
    
2. Sous l’onglet **Configuration de la jonction**, double-cliquez sur les paramètres de configuration de la jonction à modifier. Notez que vous ne pouvez modifier qu’une collection de paramètres à la fois. Si vous voulez apporter les mêmes modifications à plusieurs collections, utilisez Windows PowerShell à la place.
    
3. Dans la **boîte de dialogue Modifier la configuration de** la trunk, faites les sélections appropriées, puis cliquez sur **OK**.
    
4. La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.
    
5. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
    
6. Dans la boîte de dialogue Panneau de contrôle Skype **Entreprise Server,** cliquez sur **OK.**
    

