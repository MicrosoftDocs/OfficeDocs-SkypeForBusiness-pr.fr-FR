---
title: Planification de l’application Annonces dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planification de l’application de l’annonce dans Skype pour Business Server Voix Entreprise, qui configure quoi faire avec les appels à des numéros de téléphone non attribués dans vos organisations. Cela inclut les conditions requises pour les fichiers audio.
ms.openlocfilehash: c7ed700c749f1d5692b78c931e225fee5d0497be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-the-announcement-application-in-skype-for-business-2015"></a>Planification de l’application Annonces dans Skype Entreprise 2015
 
Planification de l’application de l’annonce dans Skype pour Business Server Voix Entreprise, qui configure quoi faire avec les appels à des numéros de téléphone non attribués dans vos organisations. Cela inclut les conditions requises pour les fichiers audio.
  
Le Skype pour application d’annonce du serveur Business vous permet de configurer la gestion des appels téléphoniques entrants lorsque le numéro composé est valide pour votre organisation, mais qu’il n’est pas affecté à un utilisateur ou d’un téléphone. Vous pouvez transférer ces appels vers une destination prédéterminée (numéro de téléphone, URI SIP ou messagerie vocale), lire une annonce audio, ou les deux. L’application d’annonce permet d’éviter les situations dans lesquelles un appelant compose un mauvais numéro et entend une tonalité de ligne occupée, ou lorsque le client SIP reçoit un message d’erreur. Cette section contient des informations de planification qui sont spécifiques à l’application de l’annonce
  
Lorsque vous déployez l’application de l’annonce, vous devez configurer une table de numéros non attribuée qui détermine l’action à entreprendre lorsqu’une personne compose un numéro non assigné. La table des numéros non attribuée contient des plages de numéros de téléphone qui sont valides pour l’organisation et spécifie quelle application annonce gère chaque plage. Lorsqu’un appelant compose un numéro de téléphone qui est valide pour votre organisation, mais qui n’est pas affecté à tout, Skype pour Business Server recherche le nombre dans la table de routage numéro non attribué, identifie une plage qui est comprise dans le nombre et achemine l’appel à la Application d’annonce spécifiée pour cette plage. L’application annonce répond à l’appel et émet un message audio (si vous avez configuré pour cela) puis déconnecte de l’appel ou transfère vers une destination prédéfinie, par exemple à un opérateur. Vous pouvez utiliser Skype pour les applets de commande Business Server Management Shell pour configurer plusieurs messages audio ou pour transférer des destinations.
  
La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Si vous avez des numéros spécifiques qui ne sont plus utilisés et que vous voulez lire des messages personnalisés pour chacun d’eux, vous pouvez entrer ces numéros spécifiques dans la table des numéros non attribués. Par exemple, si vous avez changé le numéro du bureau de service client, vous pouvez entrer l’ancien numéro du service client et l’associer à une annonce qui indique le nouveau. Si vous voulez lire un message général à quiconque appelle un numéro non attribué (comme celui d’un employé ayant quitté votre organisation), vous pouvez entrer des plages pour toutes les extensions valides de votre organisation. La table des numéros non attribués est appelée à chaque fois qu’un appelant compose un numéro qui n’est pas actuellement attribué.
  
## <a name="deployment-and-requirements"></a>Déploiement et exigences

Application de l’annonce d’estimée est automatiquement installée avec l’application de groupe de la réponse. Les applications de l’annonce et le groupe de réponse sont des composants standard d’un déploiement de Voix Entreprise : lors du déploiement de Voix Entreprise, ces deux applications sont déployées automatiquement. 
  
### <a name="software-requirements"></a>Configuration logicielle requise

Tous les serveurs en édition Standard ou des serveurs frontaux qui exécutent l’application de l’annonce doivent être installé pour les serveurs exécutant Windows Server 2008 R2, ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 Windows Media Format Runtime ou Windows Server 2012 R2. Pour Windows Server 2008 R2, Windows Media Format Runtime est installé dans le cadre de l’expérience utilisateur Windows. Windows Media Format Runtime ou Microsoft Media Foundation est requise pour les fichiers Audio Windows Media (.wma) que l’application annonce joue pour la musique et des annonces. 
  
### <a name="port-requirements"></a>Configuration requise pour les ports

L’application d’annonce utilise le **Port 5071** pour les requêtes d’écoute SIP.
    
> [!NOTE]
> Ce port est le paramètre par défaut, que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer** . Pour plus d’informations sur cette applet de commande, consultez le Skype pour obtenir une documentation Business Server Management Shell.
  
### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application d’annonce prend en charge le format de fichier Wave (.wav) et l’audio Windows Media (.wma) format de fichier pour la musique et des annonces. Configuration requise du fichier audio pour l’application de l’annonce est les mêmes que pour l’application de groupe de la réponse. Pour plus d’informations, reportez-vous à la section [Exigences techniques pour les groupes de réponse](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).
  

