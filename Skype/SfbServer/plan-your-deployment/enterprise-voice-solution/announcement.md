---
title: Planification de l’application Annonces dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planification de l’application d’annonce dans Skype pour Business Server Enterprise Voice, qui configure comment traiter les appels téléphoniques aux numéros de téléphone non attribués dans votre organisation. Cela inclut les conditions requises pour les fichiers audio.
ms.openlocfilehash: 0a804472740d7153a26670be8f1d9982adc2b89a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-the-announcement-application-in-skype-for-business-2015"></a>Planification de l’application Annonces dans Skype Entreprise 2015
 
Planification de l’application d’annonce dans Skype pour Business Server Enterprise Voice, qui configure comment traiter les appels téléphoniques aux numéros de téléphone non attribués dans votre organisation. Cela inclut les conditions requises pour les fichiers audio.
  
Le Skype pour application d’annonce de serveur d’entreprise permet de vous permet de configurer la gestion des appels téléphoniques entrants lorsque le numéro composé est valide pour votre organisation, mais n’est pas affecté à un utilisateur ou un téléphone. Vous pouvez transférer ces appels vers une destination prédéterminée (numéro de téléphone, URI SIP ou messagerie vocale), lire une annonce audio, ou les deux. L’application d’annonce permet d’éviter les situations dans lesquelles un appelant compose un mauvais numéro et entend une tonalité de ligne occupée, ou lorsque le client SIP reçoit un message d’erreur. Cette section contient des informations spécifiques à l’application d’annonce de planification
  
Lorsque vous déployez l’application d’annonce, vous devez configurer une table des numéros non attribuée qui détermine l’action à effectuer lorsqu’une personne compose un numéro non attribué. La table des numéros non attribuée contient des plages de numéros de téléphone valides pour l’organisation et spécifie l’application d’annonce gère chaque plage. Lorsqu’un appelant compose un numéro de téléphone qui est valide pour votre organisation, mais n’est pas affecté à tout le monde, Skype pour Business Server recherche le numéro dans la table de routage numéro non attribué, identifie la plage est comprise dans le nombre et achemine l’appel vers la Application d’annonce spécifiée pour cette plage. L’application d’annonce répond à l’appel et lit un message audio (si vous avez configuré pour cela) puis déconnecte l’appel ou transfère vers une destination prédéterminée, comme dans un opérateur. Vous pouvez utiliser Skype pour les applets de commande Business Server Management Shell pour configurer plusieurs messages audio ou transférer des destinations.
  
La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Si vous avez des numéros spécifiques qui ne sont plus utilisés et que vous voulez lire des messages personnalisés pour chacun d’eux, vous pouvez entrer ces numéros spécifiques dans la table des numéros non attribués. Par exemple, si vous avez changé le numéro du bureau de service client, vous pouvez entrer l’ancien numéro du service client et l’associer à une annonce qui indique le nouveau. Si vous voulez lire un message général à quiconque appelle un numéro non attribué (comme celui d’un employé ayant quitté votre organisation), vous pouvez entrer des plages pour toutes les extensions valides de votre organisation. La table des numéros non attribués est appelée à chaque fois qu’un appelant compose un numéro qui n’est pas actuellement attribué.
  
## <a name="deployment-and-requirements"></a>Déploiement et exigences

Application d’annonce estimée est automatiquement installée avec l’application Response Group. Les applications de l’annonce et Response Group sont des composants standard d’un déploiement d’Enterprise Voice : lorsque vous déployez Enterprise Voice, ces deux applications sont déployés automatiquement. 
  
### <a name="software-requirements"></a>Configuration logicielle requise

Tous les serveurs frontaux ou serveurs Standard Edition qui exécutent l’application d’annonce doivent avoir Windows Media Format Runtime installé pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows. Module d’exécution du Format Windows Media ou Microsoft Media Foundation est requise pour les fichiers Audio Windows Media (.wma) qui joue l’application d’annonce pour la musique et des annonces. 
  
### <a name="port-requirements"></a>Configuration requise pour les ports

L’application d’annonce utilise le **Port 5071** pour les demandes d’écoute SIP.
    
> [!NOTE]
> Ce port est le paramètre par défaut, que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer** . Pour plus d’informations sur cette applet de commande, voir le Skype pour la documentation sur Business Server Management Shell.
  
### <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application d’annonce prend en charge le format de fichier Wave (.wav) et audio Windows Media (.wma) format de fichier de musique et des annonces. Exigences pour l’application d’annonce les fichiers audio sont les mêmes que pour l’application Response Group. Pour plus d’informations, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).
  

