---
title: Modifier le développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Vous pouvez modifier les paramètres du serveur de périphérie ou du pool de bords en configurant les propriétés suivantes :'
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697379"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Modifier le développeur des paramètres de l’ordinateur Edge pour Lync Server 2010
 
Vous pouvez modifier les paramètres du serveur de périphérie ou du pool de bords en configurant les propriétés suivantes : 
  
 **Général**
  
- Nom de domaine **complet (FQDN**) du pool interne : il s’agit de l’identité du serveur Edge ou du pool Edge, tel que défini dans l’enregistrement DNS (Domain Name System) (A ou AAAA pour IPv6).
    
- Sélectionnez **activer la Fédération pour ce pool Edge (port 5061)** si vous voulez activer le serveur Edge ou le pool de périphérie pour la Fédération avec d’autres partenaires de protocole d’initiation de session.
    
    > [!IMPORTANT]
    > Vous pouvez uniquement définir un serveur Edge ou un pool Edge pour la Fédération. La configuration affichée dans la capture d’écran associée indique qu’un autre serveur Edge ou pool d’arêtes est déjà configuré pour la Fédération. L’enregistrement SRV DNS pour la Fédération (_sipfederationtls. _tcp.\< nom\>de domaine externe) pointe vers le serveur de périphérie ou le pool de bords pour la Fédération. 
  
- Le **port de réplication de configuration interne (https)**, par défaut sur le port TCP 4443, est le port que la copie locale (qui est locale vers la serveur Edge) du magasin de gestion central est répliquée. La copie locale du magasin de gestion central figure dans la base de données **RTCLOCAL** du serveur SQL sur chaque ordinateur. La réplication est unidirectionnelle, lancée à partir du serveur de gestion central (ou, du serveur frontal ou du pool frontal qui conserve le rôle serveur central de gestion) sur les serveurs de périphérie et est un port d’interface interne.
    
  **Sélection du saut suivant**
  
- Sélectionnez pour la liste votre **pool de sauts suivant**. Vous définissez un réalisateur, un pool de réalisateurs, un serveur frontal ou un pool frontal pour assumer ce rôle. Le pool de prochains tronçons est le serveur ou le pool de serveurs qui acceptera les messages SIP entrants à partir de l’interface interne du serveur Edge ou du pool de périphériques et envoyer le SIP sortant vers l’interface interne latérale.
    
    > [!NOTE]
    > Le directeur est un rôle facultatif et, si vous décidez de ne pas déployer les directeurs, les serveurs frontaux (ordinateur ou pool unique) assument le rôle de directeur. 
  
  **Paramètres externes**
  
Cette section des propriétés vous permet d’apporter des modifications aux propriétés des paramètres externes du serveur Edge ou du pool Edge. Vous pouvez modifier les propriétés suivantes :
  
- Activez les cases à cocher Activer les noms **de domaine complet et adresse IP pour les conférences Web et A/V** , si vous voulez attribuer des adresses IP distinctes et des noms de domaine complets à chaque service de serveur Edge.
    
    > [!NOTE]
    > Si vous choisissez de ne pas activer la case à cocher, vous devez utiliser des ports séparés pour chaque service Edge. Chaque service Edge partage le nom de domaine complet défini pour le service Edge d’accès et utilise par conséquent la même adresse IP. Chaque service Edge doit être identifié de façon unique par une adresse IP distincte et le même port, ou par la même adresse IP et les mêmes valeurs de port uniques. 
  
- Le **fait de sélectionner service Edge a/v est activé** si vous souhaitez configurer le service Edge a/v pour qu’il utilise une adresse privée ou une autre adresse qui sera masquée sur un appareil de traduction d’adresses réseau (NAT).
    
- Pour modifier le **service Edge d’accès**, vous devez définir le **nom de domaine complet du pool** pour le service Edge d’accès tel que défini dans les enregistrements DNS par hôte (A et aaaa si le protocole IPv6 est utilisé) et une valeur de port.
    
- Pour modifier le **service Edge de conférence Web**, vous devez définir un **nom de domaine complet (FQDN** ) de pool pour le service Edge de conférence Web tel que défini dans les enregistrements DNS par hôte (A et aaaa si le protocole IPv6 est utilisé) et une valeur de port
    
- Pour modifier le **service Edge a/v**, vous devez définir un **nom de domaine complet (FQDN** ) de pool pour le service Edge a/v, tel que défini dans les enregistrements DNS par hôte (A et aaaa si le protocole IPv6 est utilisé) et une valeur de port
    
    > [!IMPORTANT]
    > Si vous avez activé la case à cocher **activer le nom de domaine complet (FQDN) et l’adresse IP pour les conférences Web et A/V** Attribuez des ports distincts à chacun des trois services Edge.
  
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  

