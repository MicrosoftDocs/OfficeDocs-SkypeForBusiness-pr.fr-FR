---
title: Partage d’écran vidéo pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informations de configuration et de planification de Skype entreprise Server pour le partage d’écran vidéo (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009567"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Partage d’écran vidéo pour Skype entreprise Server 
 
Le partage d’écran basé sur la vidéo (VbSS) dans Skype entreprise Server 2015 est désormais disponible en téléchargement : [mise à jour cumulative KB3061064 pour Skype entreprise server 2015](https://www.microsoft.com/download/details.aspx?id=47690). VbSS est inclus dans Skype entreprise Server 2019.
  
Le partage d’écran basé sur la vidéo, ou VbSS, a été augmenté du partage d’écran Lync. La différence entre VbSS et le partage d’écran traditionnel est qu’il y a à faire avec les protocoles sous-jacents utilisés, et ce qu’ils utilisent dans Excel. Le partage d’écran utilise le protocole RDP (Remote Desktop Protocol), qui est parfait pour créer des milliers de sessions 1-à-1 entre les ordinateurs des personnes. La technologie plus récente, VbSS, utilisera le protocole UDP (User Datagram Protocol).
  
Skype entreprise Server souhaitait améliorer les conversations 1-à-1 de personnes, ainsi que les conversations et les expériences de réunions entre plusieurs personnes. VbSS utilise la plateforme multimédia (qui s’appuie sur le protocole UDP comme protocole sous-jacent), avec l’objectif d’améliorer les temps de démarrage de la vidéo, la qualité de l’affichage de ce que vous regardez (en particulier si ce que vous regardez se déplace rapidement) et la fiabilité globale.
  
Une partie de l’objectif de l’amélioration du partage d’écran est que les transitions entre VbSS et RDP sont aussi transparentes que possible lorsqu’elles se produisent. Étant donné qu’VbSS est une mise à jour de la technologie sous-jacente utilisée dans le partage d’écran pour Skype entreprise Server, il peut s’avérer difficile de détecter la technologie que vous utilisez, sauf si vous examinez les détails SIP dans le trafic réseau ou si vous partagez du contenu qui mouvement rapide ou 3D. Si, par exemple, votre espace de travail comporte un grand nombre de clients hérités, RDP sera toujours disponible pour vos réunions et vos conversations. Skype entreprise Server utilise la logique interne pour déterminer les deux méthodes (VbSS ou partage d’écran traditionnel) à appliquer lorsque les clients se connectent. Le protocole RDP peut être remplacé par VbSS lorsque la situation l’exige, afin que votre expérience de visualisation ne soit pas interrompue.
  
## <a name="planning"></a>Planification

### <a name="vbss-pros-and-cons"></a>Avantages et inconvénients de VbSS

Le passage à VbSS vise à apporter trois améliorations clés :
  
1. Effectuer un partage d’écran (jusqu’à 5%) plus fiable qu’avec RDP seul.

2. Faites en sorte que la configuration de session et l’expérience vidéo soient plus rapides par rapport à la version RDP seule (installation en une fois par seconde, avec une amélioration de 6:1 dans les images par seconde).

3. Fonctionne bien mieux que RDP dans des conditions de bande passante étroite, même lors du partage de contenu à haut débit, tel que des graphiques 3D.
    
N’oubliez pas que ces chiffres dépendent de l’intégrité et du réglage des performances de votre réseau, et peuvent impliquer des réseaux externes pour vous-même, si vos clients se trouvent sur des appareils mobiles.
  
Vous devez également savoir que la fidélité, la vitesse et l’efficacité de votre contenu partagé ont été compromises. Dans la plupart des cas, cette opération ne sera pas facilement visible par les utilisateurs.
  
### <a name="ports-and-protocols"></a>Ports et protocoles

**Ports serveur requis**

|**Rôle serveur**|**Nom du service**|**Port ou plage de ports**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|Serveurs frontaux  <br/> |Service de partage d’application Skype entreprise Server  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Service de partage d’application Skype entreprise Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
   
**Ports client requis**

|**Composant**|**Plage de ports**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Partage d’application.  <br/> |
   
Si QoS est activé pour les ports multimédias suivants et que VbSS est également activé, pendant une conférence qui inclut le partage de bureau, le AS MCU utilisera les paramètres de port vidéo indiqués en gras ci-dessous pour le trafic de partage d’écran. 
  
> [!IMPORTANT]
> Ces paramètres sont un cas particulier, et ces paramètres exacts doivent être utilisés lors de l’implémentation de ces deux fonctionnalités. Cela remplace les autres paramètres recommandés dans la [documentation de QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx). Pour le partage d’application, vous devez également spécifier ASMCUSVC. exe dans l’objet de stratégie de groupe QoS en plus de définir ces valeurs de port. 
  
**Paramètres QoS du serveur d’applications/VbSS requis**

|**Property**|**Valeur de port**|**Protocole**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |DATAGRAMME  <br/> |
|AudioPortCount  <br/> |8348  <br/> |DATAGRAMME  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |DATAGRAMME  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |DATAGRAMME  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planification de la capacité

Chaque serveur frontal exécutant Skype entreprise Server 2015 mise à jour cumulative 2 (CU2) ou version ultérieure prend en charge jusqu’à 375 participants pour le partage d’écran à l’aide de RDP (bien que seulement 250 par réunion). Cette capacité ne change pas après la CU3, lorsque VbSS est introduit et utilisé.
  
Cela étant dit, nous avons réalisé des tests de performances et de stress dans notre laboratoire, et les mesures suivantes doivent également être prises en compte en ce qui concerne votre propre déploiement (en fonction de l’utilisation, bien évidemment).
  
En supposant
  
- Vous utilisez Skype entreprise Server 2015 CU2 ou une version ultérieure dans votre déploiement.
    
- Tous les utilisateurs de votre environnement Skype entreprise Server ont une résolution d’écran supérieure à 1920x1080.
    
À pleine capacité (comme indiqué ci-dessus, est 375 les participants au partage d’écran par serveur frontal au total, même 250 par réunion), votre serveur frontal peut utiliser environ 89% de la carte réseau 1 Gigabit. Cela est dû au fait que la technologie de partage d’écran existante dans Skype entreprise Server CU2 (RDP) transmet le contenu à l’écran à la résolution native du PC du présentateur. Ainsi, avec des résolutions d’écran supérieures, il se peut que vous rencontriez déjà des goulots d’étranglement du réseau pour le partage d’écran avec Skype entreprise Server 2015 CU2.
  
Pour atténuer cela, une ou plusieurs des options suivantes peuvent être utiles :
  
- Mettez à niveau votre serveur frontal à partir d’une carte réseau 1 Gigabit vers une carte Ethernet 10 Gigabit.

- Augmentez le nombre de serveurs frontaux pour équilibrer la charge du trafic.

- Limitez la bande passante utilisée pour VbSS et RDP en plaçant un cap sur la bande passante maximale utilisée par les deux canaux.
    
Les chiffres de ce tableau sont influencés par les réseaux individuels et par le contenu partagé. Effectuez un test pour établir des configurations de référence pour votre réseau ou vos réseaux.
  
|**Contenu 1080p**|**Moyenne RDP**|**PIC RDP**|**Moyenne VbSS**|**PIC VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PowerPoint  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|DAO  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vidéo  <br/> |5mbps  <br/> |7mbps  <br/> |1,3 Mbits/s  <br/> |2,2 Mbits/s  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Besoins en bande passante réseau pour le trafic multimédia

La bande passante VbSS est la suivante :
  
|**Codec vidéo**|**Résolution et proportions**|**Vitesse de transmission de la charge utile vidéo maximale (Kbits/s)**|**Vitesse de transmission de la charge utile vidéo minimale (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920x1080 (16:9)  <br/> (Les proportions dépendent de la résolution du moniteur du partage et ne seront pas toujours 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Clients et serveurs pris en charge

Le partage d’écran basé sur la vidéo nécessite Skype entreprise Server 2015 CU3 ou une version ultérieure, ainsi qu’une version actuelle des clients de prise en charge figurant dans la [comparaison des fonctionnalités de client mobile pour Skype entreprise](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) et la [prise en charge des réunions](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Dans certaines situations, le partage d’écran passe à RDP, comme suit :
  
- Si votre compte est hébergé dans un environnement où le ASMCU ne correspond pas à la version minimale prise en charge par VbSS.
- Si une personne qui utilise une version plus ancienne du client Skype entreprise rejoint votre session, par exemple toute personne utilisant une version de client Windows inférieure à 16.0.6330.1000, des périphériques du système de salle Skype entreprise ou des applications pour Skype entreprise mobile. 
- Si un utilisateur partage à partir de Skype entreprise Web App.
- Si une personne utilise Skype entreprise sur Mac et qu’elle n’est pas hébergée sur Skype entreprise Online ou Skype entreprise Server 2015 avec la mise à jour cumulative de juillet 2018 (ou version ultérieure).
- Si un utilisateur démarre un programme ou un partage Windows.
- Si une personne commence à enregistrer la session.
- Si une personne appelle le contrôle d’écran distant pendant la session. 
- Réunions avec plus de 250 participants (où VbSS n’est actuellement pas pris en charge).

N’oubliez pas qu’une fois que la session passe au protocole RDP, elle n’est pas transférée vers VbSS. Une fois encore, la transition de VbSS est censée être transparente et, avec espoir, ne sera pas facile à détecter dans la plupart des situations.
    
> [!NOTE]
> Il n’est pas pris en charge pour bloquer ou tenter de bloquer la transition de VbSS vers RDP dans Skype entreprise. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Activation, désactivation et configuration de VbSS

Une fois que vous avez installé la mise à jour cumulative 3 (CU3) de Skype entreprise Server 2015 ou une version ultérieure, tous vos utilisateurs seront activés pour les VbSS 1-à-1 et multi-partie par défaut. Cela peut vous être problématique si vous n’avez pas la possibilité de l’activer pour tous vos utilisateurs. Dans ce cas, vous pouvez utiliser ces étapes pour désactiver les utilisateurs (les étapes d’activation des utilisateurs suivront) :
  
### <a name="how-to-disable-users-from-using-vbss"></a>Comment empêcher les utilisateurs d’utiliser VbSS

- Vous pouvez attribuer une stratégie utilisateur qui n’autorise pas les VbSS à tous les utilisateurs qui ne doivent pas utiliser VbSS en exécutant cette cmdlet dans la console de gestion Skype entreprise (remplacez [PolicyName] par la stratégie pour laquelle vous effectuez cette opération) :
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale, qui affectera tous les utilisateurs sans stratégie attribuée :
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Pour plus d’informations sur cette commande, reportez-vous à [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous devez désactiver complètement VbSS, vous pouvez exécuter la commande suivante :
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Pour plus d’informations sur cette commande, reportez-vous à [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans une réunion Skype entreprise à plusieurs, tous les points de terminaison du client respectent le paramètre de stratégie pour l’organisateur de la réunion. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Comment permettre aux utilisateurs d’utiliser VbSS

- Vous pouvez affecter une stratégie utilisateur spécifique qui autorise l’VbSS à tous les utilisateurs qui doivent utiliser VbSS en exécutant cette cmdlet dans la console de gestion Skype entreprise (remplacez [PolicyName] par la stratégie pour laquelle vous effectuez cette opération) :
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale, qui affectera tous les utilisateurs sans stratégie attribuée :
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Pour plus d’informations sur cette commande, reportez-vous à [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous devez réactiver VbSS après l’avoir désactivée (il est activé par défaut), vous pouvez exécuter la commande suivante :
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Pour plus d’informations sur cette commande, reportez-vous à [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans une réunion Skype entreprise multipartie, tous les points de terminaison du client respectent le paramètre de stratégie pour l’organisateur de la réunion. 
  
## <a name="see-also"></a>Voir aussi

[Mise à jour cumulative de Skype entreprise Server 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[Le partage d’écran basé sur la vidéo (VBSS) est disponible dans Skype entreprise Server 2015](https://support.microsoft.com/kb/3170163)
