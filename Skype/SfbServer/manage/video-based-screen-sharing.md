---
title: Partage d’écran vidéo pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informations de planification et de configuration de Skype entreprise Server pour le partage d’écran vidéo (VbSS)
ms.openlocfilehash: 00c699f9a26d82506bd13fefe0e6f3e53f7b86bf
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992391"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Partage d’écran vidéo pour Skype Entreprise Server 
 
Le partage d’écran vidéo (VbSS) dans Skype entreprise Server 2015 est désormais disponible en téléchargement : [Skype entreprise server 2015 cumulative update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690). VbSS est inclus dans Skype entreprise Server 2019.
  
Le partage d’écran vidéo, ou VbSS, a grandi depuis le partage d’écran Lync. La différence entre VbSS et le partage d'écran traditionnel réside dans les protocoles sous-jacents utilisés et dans ce qu'ils permettent de réaliser. Le partage d'écran utilise le protocole RDP (Remote Desktop Protocol), qui est parfait pour créer des centaines de sessions un-à-un entre plusieurs ordinateurs individuels. Une nouvelle technologie, VbSS, utilisera le protocole User Datagram Protocol (UDP).
  
Skype entreprise Server voulait améliorer les conversations entre les utilisateurs et les réunions de 1 à 2 personnes et leurs expériences de réunion et d’autres utilisateurs. VbSS utilise la plate-forme multimédia (qui utilise UDP comme protocole sous-jacent), dont l'objectif est d'améliorer les délais de démarrage de vos vidéos, la qualité d'affichage du contenu que vous regardez (en particulier si la vitesse des images que vous regardez est élevée) et la fiabilité globale.
  
Un des objectifs de l'amélioration du partage d'écran consiste à rendre les transitions entre VbSS et RDP les plus transparentes possibles. Dans la mesure où VbSS est une mise à jour de la technologie sous-jacente qui est utilisée dans le partage d’écran pour Skype entreprise Server, il peut être difficile de détecter la technologie que vous utilisez, sauf si vous examinez les détails SIP dans le trafic réseau ou si vous partagez du contenu déplacement rapide ou 3D. Par exemple, si votre entreprise possède un grand nombre de clients hérités, le protocole RDP restera disponible en tant que service pour vos réunions et vos conversations. Skype entreprise Server utilise la logique interne pour déterminer les deux méthodes (VbSS ou le partage d’écran traditionnel) à appliquer lorsque les clients se connectent. RDP peut se substituer à VbSS, ce qu'il fera lorsque la situation l'exige, afin de vous garantir une expérience de visionnage sans interruption.
  
## <a name="planning"></a>Planification

### <a name="vbss-pros-and-cons"></a>VbSS : pour et contre

Le passage à VbSS vise trois améliorations majeures :
  
1. Rendre le partage d'écran (jusqu'à 5 %) plus fiable par rapport à RDP seul.

2. Accélérer la configuration de la session et l'expérience vidéo par rapport à RDP seul (configuration deux fois plus rapide, avec un affichage d'images par seconde amélioré de 6:1).

3. Une efficacité largement supérieure à RDP avec une bande passante réduite, même en cas de partage de contenu à vitesse élevée, comme des images 3D.
    
Gardez à l'esprit que ces chiffres reflètent l'intégrité et les performances propres de votre réseau, et peuvent impliquer des réseaux externes au vôtre, dans le cas où vos clients utilisent des appareils mobiles.
  
Sachez également que la fiabilité, la vitesse et l'efficacité prévalent généralement sur la fidélité/netteté. Ceci ne sera pas facilement visible pour vos utilisateurs.
  
### <a name="ports-and-protocols"></a>Ports et protocoles

**Ports serveur requis**

|**Rôle serveur**|**Nom du service**|**Port ou plage de ports**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|serveurs frontaux  <br/> |Service de partage d’application Skype entreprise Server  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Service de partage d’application Skype entreprise Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
   
**Ports clients requis**

|**Composant**|**Plage de ports**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Partage d’application.  <br/> |
   
Si la qualité de service (QoS) est activée pour les ports multimédias suivants et que VbSS est également activé, lors d’une conférence qui inclut le partage de bureau, la fonction MCU utilise les paramètres de port vidéo indiqués en gras ci-dessous pour le trafic de partage d’écran. 
  
> [!IMPORTANT]
> Ces paramètres sont des cas particuliers, et ces paramètres exacts doivent être utilisés lors de l’implémentation de ces deux fonctionnalités. Ce paramètre a pour priorité d’autres paramètres recommandés dans la [documentation pour QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). Pour le partage d’application, vous devez également spécifier ASMCUSVC. exe dans l’objet GPO QoS en plus de définir ces valeurs de port. 
  
**Application Server QoS/VbSS requise**

|**Propriété**|**Valeur de port**|**Protocole**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planification de capacité

Chaque serveur frontal exécutant Skype entreprise Server 2015 cumulative Update 2 (CU2) ou une version ultérieure prend en charge jusqu’à 375 participants pour le partage d’écran à l’aide du protocole RDP (même uniquement 250 par réunion). Cette capacité ne modifie pas la situation après CU3, lorsque VbSS est mis en place et utilisé.
  
Ceci étant dit, des tests de contrainte et de performances ont été réalisés dans notre laboratoire et les mesures suivantes doivent également être prises en compte dans le cadre de votre propre déploiement (en fonction, bien sûr, de l'usage).
  
Supposons les points suivants :
  
- Vous utilisez Skype entreprise Server 2015 CU2 ou une version ultérieure dans votre déploiement.
    
- La résolution d’écran de tous les utilisateurs de votre environnement Skype entreprise Server est supérieure à 1920x1080.
    
En fonction de la capacité totale (comme indiqué ci-dessus, est le partage d’écran 375 de la part des participants au serveur frontal au total, même uniquement 250 par réunion), il est possible que votre serveur frontal utilise ~ 89% de la carte réseau 1 Go. En effet, la technologie de partage d’écran existante dans Skype entreprise Server CU2 (RDP) transmet le contenu à l’écran à la résolution native du PC du présentateur. Par conséquent, si vous avez une meilleure résolution d’écran, il est possible que vous rencontriez des goulots d’étranglement réseau pour le partage d’écran avec Skype entreprise Server 2015 CU2.
  
Pour empêcher cela, vous pouvez procéder de l'une des manières suivantes :
  
- Mettez à niveau votre serveur frontal d’une carte réseau 1 Gigabit vers une carte Ethernet 10 Gigabit.

- Augmentez le nombre de serveurs frontaux pour équilibrer le trafic.

- Limitez la bande passante (vitesse de transmission) utilisée pour VbSS et RDP en imposant une bande passante maximale à utiliser par les canaux.
    
Les chiffres figurant dans cette table subissent l’influence des réseaux individuels et des contenus partagés. Veuillez effectuer un test afin de déterminer les lignes de base de votre ou de vos réseau(x).
  
|**Contenu 1080p **|**Moyenne RDP**|**Pic RDP**|**Moyenne VbSS**|**Pic VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vidéo  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Configuration requise de la bande passante pour le trafic multimédia

La bande passante pour VbSS est :
  
|**Codec vidéo**|**Résolution et proportions**|**Vitesse de transmission de la charge utile vidéo maximale (Kbits/s)**|**Vitesse de transmission de la charge utile vidéo minimale (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1 920x1 080 (16:9)  <br/> (La proportion dépend de la résolution du moniteur de l'utilisateur qui partage son écran et ne sera pas toujours de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Clients et serveurs pris en charge

Le partage d’écran vidéo nécessite Skype entreprise Server 2015 CU3 ou une version ultérieure, ainsi qu’une version actuelle des clients de prise [en charge](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)répertoriés dans [les fonctionnalités du client mobile](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) . 
  
Dans certains cas, le partage d’écran va basculer vers RDP, comme suit :
  
- Si votre compte est hébergé dans un environnement où l'ASMCU n'est pas conforme à la version minimale prenant en charge VbSS.
- Si une personne qui utilise une ancienne version du client Skype entreprise rejoint votre session (par exemple, toute personne utilisant une version de client Windows inférieure à 16.0.6330.1000, des appareils système de salle Skype entreprise ou des applications mobiles Skype entreprise). 
- Si un utilisateur partage à partir de l’application Web Skype entreprise.
- Si une personne utilise Skype entreprise sur Mac et qu’elle n’est pas hébergée sur Skype entreprise Online ou Skype entreprise Server 2015 avec la mise à jour cumulative de juillet 2018 (ou une version ultérieure).
- Si une personne démarre un programme ou un partage Windows.
- Si une personne démarre l’enregistrement de la session.
- Si un utilisateur appelle le contrôle d'appel distant lors de la session. 
- Réunions avec plus de 250 participants (où VbSS n'est actuellement pas pris en charge).

Sachez qu'une fois que la session passe à RDP, elle ne reviendra pas à VbSS. Encore une fois, la transition depuis VbSS est censée être transparente et, si possible, elle ne sera pas facile à détecter dans la plupart des situations.
    
> [!NOTE]
> Il n’est pas pris en charge pour bloquer ou bloquer, transition de VbSS vers RDP dans Skype entreprise-partage d’écran. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Activation, désactivation et configuration de VbSS

Une fois que vous avez installé la mise à jour cumulative 3 de Skype entreprise Server 2015 (CU3) ou une version ultérieure, tous vos utilisateurs seront activés par défaut pour 1 à-1 ou plusieurs VbSS. Ceci peut vous poser problème si vous ne souhaitez pas, pour une raison quelconque, que cette fonctionnalité soit activée pour tous vos utilisateurs. Dans ce cas, vous pouvez suivre les étapes suivantes pour désactiver des utilisateurs (les étapes permettant d'activer des utilisateurs seront décrites par la suite) :
  
### <a name="how-to-disable-users-from-using-vbss"></a>Comment désactiver la fonctionnalité VbSS pour des utilisateurs :

- Vous pouvez affecter une stratégie de l’utilisateur qui n’autorise pas les utilisateurs à VbSS en exécutant cette cmdlet dans la console de gestion Skype entreprise (remplacez [PolicyName] par la stratégie que vous voulez appliquer à cette fin) :
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale qui affectera l'ensemble des utilisateurs sans avoir attribué une stratégie :
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous souhaitez désactiver complètement VbSS, exécutez la commande suivante :
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans une réunion Skype entreprise à plusieurs parties, tous les points de terminaison client respectent le paramètre de stratégie de l’organisateur de la réunion. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Comment activer la fonctionnalité VbSS pour des utilisateurs :

- Vous pouvez assigner une stratégie d’utilisateur spécifique qui permet à VbSS d’utiliser des VbSS en exécutant cette cmdlet dans la console de gestion Skype entreprise (remplacez [PolicyName] par la stratégie que vous avez utilisée pour cela) :
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale qui affectera l'ensemble des utilisateurs sans avoir attribué une stratégie :
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous souhaitez rétablir VbSS après l'avoir désactivé (la fonctionnalité est activée par défaut), vous pouvez exécuter la commande suivante :
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans une réunion Skype entreprise à plusieurs parties, tous les points de terminaison client respectent le paramètre de stratégie de l’organisateur de la réunion. 
  
## <a name="see-also"></a>Voir aussi

[Mise à jour cumulative 2015 de Skype entreprise Server KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[Le partage d’écran vidéo (VBSS) est disponible dans Skype entreprise Server 2015](https://support.microsoft.com/en-us/kb/3170163)
