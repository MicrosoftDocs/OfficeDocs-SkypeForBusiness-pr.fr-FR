---
title: Partage d’écran vidéo pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 'Skype pour Business Server 2015 les informations de planification et de configuration pour vidéo partage d’écran (VbSS), qui est désormais disponible au téléchargement : Skype pour le KB3061064 de mise à jour Cumulative Business Server 2015.'
ms.openlocfilehash: 21b7868efb9b1a6621aa85cae277114629d67551
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="video-based-screen-sharing-for-skype-for-business-server-2015"></a>Partage d’écran vidéo pour Skype Entreprise Server 2015
 
Skype pour Business Server 2015 les informations de planification et de configuration pour vidéo partage d’écran (VbSS), qui est désormais disponible au téléchargement : [Skype pour le KB3061064 de mise à jour Cumulative Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=47690).
  
Vidéo-partage d’écran, ou VbSS, a augmenté de Lync de partage d’écran. La différence entre VbSS et le partage d'écran traditionnel réside dans les protocoles sous-jacents utilisés et dans ce qu'ils permettent de réaliser. Le partage d'écran utilise le protocole RDP (Remote Desktop Protocol), qui est parfait pour créer des centaines de sessions un-à-un entre plusieurs ordinateurs individuels. Une nouvelle technologie, VbSS, utilisera le protocole User Datagram Protocol (UDP).
  
Skype pour Business Server souhaitait augmenter la-1-1 populaire et leurs conversations (multiparties) 1-à-plusieurs et d’expérience de réunions. VbSS utilise la plate-forme multimédia (qui utilise UDP comme protocole sous-jacent), dont l'objectif est d'améliorer les délais de démarrage de vos vidéos, la qualité d'affichage du contenu que vous regardez (en particulier si la vitesse des images que vous regardez est élevée) et la fiabilité globale.
  
Un des objectifs de l'amélioration du partage d'écran consiste à rendre les transitions entre VbSS et RDP les plus transparentes possibles. VbSS étant une mise à jour à la technologie sous-jacente qui est utilisée dans le partage de Skype pour Business Server de l’écran, il peut être difficile à détecter quelle technologie vous êtes exploitant, sauf si vous examinez les détails SIP dans le trafic réseau, ou que vous partagez du contenu qui est un déplacement rapide ou 3D. Si, par exemple, votre espace de travail a un grand nombre de clients hérités, RDP sera disponible comme sécurité intégrée pour vos réunions et vos conversations. Skype pour Business Server utilise la logique interne de déterminer laquelle des deux méthodes (VbSS ou partage d’écran traditionnel) à appliquer lorsque les clients se connectent. RDP peut se substituer à VbSS, ce qu'il fera lorsque la situation l'exige, afin de vous garantir une expérience de visionnage sans interruption.
  
## <a name="planning"></a>Planification

### <a name="vbss-pros-and-cons"></a>VbSS : pour et contre

Le passage à VbSS vise trois améliorations majeures :
  
1. Rendre le partage d'écran (jusqu'à 5 %) plus fiable par rapport à RDP seul.

2. Accélérer la configuration de la session et l'expérience vidéo par rapport à RDP seul (configuration deux fois plus rapide, avec un affichage d'images par seconde amélioré de 6:1).

3. Une efficacité largement supérieure à RDP avec une bande passante réduite, même en cas de partage de contenu à vitesse élevée, comme des images 3D.
    
Gardez à l'esprit que ces chiffres reflètent l'intégrité et les performances propres de votre réseau, et peuvent impliquer des réseaux externes au vôtre, dans le cas où vos clients utilisent des appareils mobiles.
  
Sachez également que la fiabilité, la vitesse et l'efficacité prévalent généralement sur la fidélité/netteté. Ceci ne sera pas facilement visible pour vos utilisateurs.
  
### <a name="ports-and-protocols"></a>Ports et protocoles

**Ports de serveur requis**

|**Rôle de serveur**|**Nom du service**|**Port ou plage de ports**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|
|serveurs frontaux  <br/> |Skype pour service de partage de l’Application serveur de Business  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype pour service de partage de l’Application serveur de Business  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
   
**Ports du client requis**

|**Composant**|**Plage de port**|**Protocole**|**Remarques**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Partage d’application.  <br/> |
   
Si QoS est activé pour les ports de media suivants et VbSS est également activé, lors d’une conférence qui inclut le partage du bureau que le MCU en tant qu’utilisent les paramètres de port vidéo illustrés en gras ci-dessous pour le trafic de partage d’écran. 
  
> [!IMPORTANT]
> Ces paramètres sont un cas particulier, et ces paramètres exactes doivent être utilisés lors de l’implémentation de ces deux fonctionnalités. Cela remplace les autres paramètres recommandés dans la [documentation relative à la qualité de service](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx). FO partage d’application vous devrez également spécifier ASMCUSVC.exe dans l’objet GPO de qualité de service en plus de définir ces valeurs de port. 
  
**Application serveur QoS/VbSS les paramètres requis**

|**Propriété**|**Valeur du port**|**Protocole**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>Planification de capacité

Chaque serveur frontal exécutant Skype pour Business Server 2015 Cumulative Update 2 (CU2) prend en charge jusqu'à 375 participants pour écran de partage à l’aide de RDP (bien que simplement 250 par réunion). Cette capacité ne modifie pas la situation après CU3, lorsque VbSS est mis en place et utilisé.
  
Ceci étant dit, des tests de contrainte et de performances ont été réalisés dans notre laboratoire et les mesures suivantes doivent également être prises en compte dans le cadre de votre propre déploiement (en fonction, bien sûr, de l'usage).
  
Supposons les points suivants :
  
- Vous utilisez Skype pour Business Server 2015 CU2 dans votre déploiement.
    
- Tous les utilisateurs dans votre Skype pour environnement Business Server ont des résolutions d’écran supérieures à 1920 x 1080.
    
À sa capacité maximale (c'est-à-dire comme indiqué ci-dessus, 375 participants de partage d’écran par un serveur frontal dans le total, mais seulement 250 par réunion), votre serveur frontal peut être utilisant ~ 89 % de la 1 Gigabit de carte réseau. C’est parce que le partage de technologie dans Skype pour Business Server CU2 (RDP) existante, écran transmet le contenu à l’écran à la résolution native de PC du présentateur. Ainsi, avec des résolutions d’écran élevées pris en compte, vous pouvez déjà rencontrer les goulots d’étranglement pour partage avec Skype pour Business Server 2015 CU2 de l’écran.
  
Pour empêcher cela, vous pouvez procéder de l'une des manières suivantes :
  
- Mettre à niveau votre serveur frontal à partir d’une carte réseau de 1 Gigabit à une carte Gigabit Ethernet de 10.

- Augmentez le nombre de serveurs frontaux pour le trafic d’équilibrage de charge.

- Limitez la bande passante (vitesse de transmission) utilisée pour VbSS et RDP en imposant une bande passante maximale à utiliser par les canaux.
    
Les chiffres figurant dans cette table subissent l’influence des réseaux individuels et des contenus partagés. Veuillez effectuer un test afin de déterminer les lignes de base de votre ou de vos réseau(x).
  
|**Contenu de 1080p**|**Moyenne RPD**|**Pic de RDP**|**Moyenne de VbSS**|**Pointe de VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 Kbits/s  <br/> |12  <br/> |100 Kbits/s  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1 Mb/s  <br/> |3mbps  <br/> |
|Vidéo  <br/> |5Mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Configuration requise de la bande passante pour le trafic multimédia

La bande passante pour VbSS est :
  
|**Codec vidéo**|**Résolution et rapport l / h**|**Vitesse de transmission de charge utile vidéo maximale (Kbits/s)**|**Vitesse de transmission minimale de charge utile vidéo (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1 920x1 080 (16:9)  <br/> (La proportion dépend de la résolution du moniteur de l'utilisateur qui partage son écran et ne sera pas toujours de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Clients et serveurs pris en charge

Partage d’écran vidéo nécessite Skype pour Business Server 2015 CU3 ou version ultérieure et une version en cours de support clients répertoriés dans la [comparaison des fonctionnalités de client Mobile pour Skype pour les entreprises](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) et la [prise en charge des réunions](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Il existe des situations où partage d’écran passera à RDP, comme celles-ci :
  
- Si votre compte est hébergé dans un environnement où l'ASMCU n'est pas conforme à la version minimale prenant en charge VbSS.
- Si une personne qui utilise une version antérieure de la Skype pour client d’entreprise joint à votre session, par exemple tout le monde à l’aide de n’importe quelle version de client Windows qui est inférieure à 16.0.6330.1000, Skype pour périphériques de système de salle Business ou Skype pour les applications métier mobiles. 
- Si un utilisateur partage depuis le Skype pour Business Web App.
- Si une personne est à l’aide de Skype pour Mac de Businesson et pas hébergée sur Skype pour l’activité en ligne.
- Si un utilisateur démarre un partage de programme/fenêtre et/ou un enregistrement lors de la session.
- Si un utilisateur appelle le contrôle d'appel distant lors de la session.

    Sachez qu'une fois que la session passe à RDP, elle ne reviendra pas à VbSS. Encore une fois, la transition depuis VbSS est censée être transparente et, si possible, elle ne sera pas facile à détecter dans la plupart des situations.
  
- Réunions avec plus de 250 participants (où VbSS n'est actuellement pas pris en charge).
    
> [!NOTE]
> Il n’est pas pris en charge au bloc, ou tentent de bloquer, passage de VbSS à RDP dans Skype pour entreprise-partage d’écran. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Activation, désactivation et configuration de VbSS

L’avantage est, une fois que vous avez installé le Skype pour Business Server 2015 Cumulative Update 3 (CU3), tous les utilisateurs seront activées pour les VbSS de 1 à 1 et plusieurs par défaut. Ceci peut vous poser problème si vous ne souhaitez pas, pour une raison quelconque, que cette fonctionnalité soit activée pour tous vos utilisateurs. Dans ce cas, vous pouvez suivre les étapes suivantes pour désactiver des utilisateurs (les étapes permettant d'activer des utilisateurs seront décrites par la suite) :
  
### <a name="how-to-disable-users-from-using-vbss"></a>Comment désactiver la fonctionnalité VbSS pour des utilisateurs :

- Vous pouvez affecter une stratégie de l’utilisateur qui n’autorise pas VbSS à tous les utilisateurs qui ne doivent pas être VbSS par l’exécution de cette cmdlet dans le Skype pour Console de gestion d’entreprise (Remplacez [PolicyName] par la stratégie que vous le faites pour) :
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale qui affectera l'ensemble des utilisateurs sans avoir attribué une stratégie :
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous souhaitez désactiver complètement VbSS, exécutez la commande suivante :
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans un Skype à plusieurs participants de la réunion d’entreprise, tous les points de terminaison clients respecte le paramètre de stratégie pour l’organisateur de la réunion. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Comment activer la fonctionnalité VbSS pour des utilisateurs :

- Vous pouvez affecter une stratégie d’utilisateur spécifique qui permet à tous les utilisateurs qui ont besoin d’utiliser la VbSS par l’exécution de cette cmdlet dans le Skype pour Console de gestion d’entreprise (Remplacez [PolicyName] par la stratégie que vous le faites pour) de VbSS :
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale qui affectera l'ensemble des utilisateurs sans avoir attribué une stratégie :
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous souhaitez rétablir VbSS après l'avoir désactivé (la fonctionnalité est activée par défaut), vous pouvez exécuter la commande suivante :
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans un multipartie Skype pour une réunion professionnelle, tous les points de terminaison clients respecte le paramètre de stratégie pour l’organisateur de la réunion. 
  
## <a name="see-also"></a>Voir aussi

#### 

[Skype pour KB3061064 de mise à jour Cumulative Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[Vidéo-partage d’écran (VBSS) est disponible dans Skype pour Business Server 2015](https://support.microsoft.com/en-us/kb/3170163)

