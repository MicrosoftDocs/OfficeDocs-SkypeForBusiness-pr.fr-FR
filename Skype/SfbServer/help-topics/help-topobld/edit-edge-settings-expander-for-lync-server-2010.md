---
title: Modifier l’expanseur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Vous modifiez les paramètres du serveur Edge ou du pool de serveurs Edge en configurant les propriétés suivantes :'
ms.openlocfilehash: b1ffc038a8995663c3a080e29fa4322928a7b214
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828897"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Modifier l’expandeur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Vous modifiez les paramètres du serveur Edge ou du pool de serveurs Edge en configurant les propriétés suivantes : 
  
 **Général**
  
- Nom de domaine complet du **pool** interne : le nom de domaine complet du pool interne est l’identité du serveur Edge ou du pool edge tel que défini dans l’enregistrement d’hôte DNS (A ou AAAA pour IPv6).
    
- Sélectionnez Activer la fédération pour ce **pool Edge (port 5061)** si vous souhaitez activer le serveur Edge ou le pool edge pour la fédération avec d’autres partenaires de protocole d’initiation de session.
    
    > [!IMPORTANT]
    > Vous ne pouvez définir qu’un seul serveur Edge ou pool edge activement pour la fédération. La configuration indiquée dans la capture d’écran associée indique qu’un autre serveur Edge ou pool de serveurs Edge est déjà configuré pour la fédération. L’enregistrement SRV DNS externe pour la fédération (_sipfederationtls._tcp. ) pointe vers le serveur Edge ou le \<external domain name\> pool edge pour la fédération. 
  
- Le port de réplication de configuration **interne (HTTPS),** par défaut sur le port TCP 4443, est le port sur le port sur qui la copie locale (c’est-à-dire, locale des serveurs Edge) du magasin central de gestion est répliquée. La copie locale du magasin central de gestion se trouve dans la base de données **RTCLOCAL** du SQL Server sur chaque ordinateur. La réplication est à sens unique, initiée à partir du serveur central de gestion (ou du serveur frontal ou du pool frontal qui détient le rôle serveur de gestion centralisée) vers les serveurs Edge et est un port d’interface interne.
    
  **Sélection du tronçon suivant**
  
- Sélectionnez dans la liste votre **Pool du tronçon suivant**. Vous définissez un directeur, un pool directeur, un serveur frontal ou un pool frontal pour assumer ce rôle. Le pool du saut suivant est le serveur ou le pool de serveurs qui acceptera les messages SIP entrants provenant de l’interface interne du serveur Edge ou du pool de serveurs Edge et enverra le SIP sortant à l’interface interne Edge.
    
    > [!NOTE]
    > Le directeur est un rôle facultatif et si vous décidez de ne pas déployer les directeurs, les serveurs frontux (un seul ordinateur ou pool) assumeront le rôle directeur. 
  
  **Paramètres externes**
  
Cette section des propriétés vous permet de modifier les propriétés des paramètres externes du serveur Edge ou du pool edge. Les propriétés suivantes peuvent être modifiées :
  
- Activez la case à cocher Activer un nom de domaine complet et une adresse IP distincts pour la conférence web et activez la case à cocher **A/V** si vous souhaitez affecter des adresses IP distinctes et des noms de domaine complets à chaque service de serveur Edge.
    
    > [!NOTE]
    > Si vous choisissez de ne pas activer la case à cocher, vous devez utiliser des ports distincts pour chaque service Edge. Chaque service Edge partagera le nom de groupe défini pour le service Edge d’accès et utilisera donc la même adresse IP. Chaque service Edge doit être identifié de manière unique soit par une adresse IP distincte et le même port, soit par la même adresse IP et des valeurs de port uniques. 
  
- Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.
    
- Pour modifier le **service Edge** d’accès, vous définissez le nom de groupe complet du **pool** pour le service Edge d’accès tel que défini dans DNS par les enregistrements d’hôte (A et AAAA si IPv6 est utilisé) et une valeur de port
    
- Pour modifier le service Edge de conférence **Web,** vous définissez un nom de pool de **FQDN** pour le service Edge de conférence Web tel que défini dans DNS par les enregistrements d’hôte (A et AAAA si IPv6 est utilisé) et une valeur de port
    
- Pour modifier le **service Edge A/V,** vous définissez un nom de pool pour le service Edge A/V tel que défini dans DNS par les enregistrements d’hôte (A et AAAA si IPv6 est utilisé) et une valeur de port 
    
    > [!IMPORTANT]
    > Si vous avez activé la case à cocher Activer un FQDN et une adresse IP distincts pour la conférence web et **A/V,** seul le FQDN du pool de services Edge d’accès sera disponible pour modification. Assignez des ports distincts à chacun des trois services Edge.
  
  **OK** permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** permet d’afficher cet écran d’aide.
  

