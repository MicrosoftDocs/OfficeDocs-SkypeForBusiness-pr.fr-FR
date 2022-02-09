---
title: Partage d’écran vidéo pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype Entreprise Server de planification et de configuration pour le partage d’écran vidéo (VbSS)
ms.openlocfilehash: 0eb381504e797879d9e4235d7ae9cce69f1a468c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396426"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Partage d’écran vidéo pour Skype Entreprise Server 
 
Le partage d’écran vidéo (VbSS) dans Skype For Business Server 2015 est désormais disponible en téléchargement : mise à jour cumulative [Skype Entreprise Server 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS est inclus dans Skype Entreprise Server 2019.
  
Le partage d’écran vidéo, ou VbSS, s’est développé en dehors du partage d’écran Lync. La différence entre VbSS et le partage d’écran traditionnel a une relation avec les protocoles sous-jacents utilisés et ce qu’ils excelent. Le partage d’écran utilise le protocole RDP (Remote Desktop Protocol), qui permet de créer des milliers de sessions 1 à 1 entre les ordinateurs des utilisateurs. Une technologie plus récente, VbSS, utilisera le protocole UDP (User Datagram Protocol).
  
Skype Entreprise Server souhaitait améliorer le 1-à-1 des utilisateurs, ainsi que leurs conversations et expériences de réunion entre plusieurs utilisateurs. VbSS utilise la plateforme multimédia (qui repose sur UDP comme protocole sous-jacent), dans le but d’améliorer les heures de début de la vidéo, la qualité d’affichage de ce que vous regardez (en particulier si ce que vous regardez est en cours de déplacement rapide) et la fiabilité globale.
  
L’un des objectifs de l’amélioration du partage d’écran est que les transitions entre VbSS et RDP soient aussi transparentes que possible lorsqu’elles se produisent. Étant donné que VbSS est une mise à jour de la technologie sous-jacente utilisée dans le partage d’écran pour Skype Entreprise Server, il peut être difficile de détecter la technologie que vous tirent parti, sauf si vous regardez des détails SIP dans le trafic réseau ou si vous partagez du contenu à déplacement rapide ou 3D. Si, par exemple, votre espace de travail possède un grand nombre de clients hérités, RDP reste disponible en tant que sécurité d’échec pour vos réunions et conversations. Skype Entreprise Server utilise une logique interne pour déterminer laquelle des deux méthodes (VbSS ou partage d’écran traditionnel) à appliquer lorsque les clients se connectent. RDP peut et sera remplacé par VbSS lorsque la situation l’exige, afin que votre expérience d’affichage ne soit pas interrompue.
  
## <a name="planning"></a>Planification

### <a name="vbss-pros-and-cons"></a>Avantages et inconvénients VbSS

Le passage à VbSS vise à apporter trois améliorations clés :
  
1. Rendre le partage d’écran (jusqu’à 5 %) plus fiable que RDP seul.

2. Accélérer l’installation de la session et l’expérience vidéo par rapport à RDP seul (installation en deux fois plus rapide, avec une amélioration de 6:1 des images par seconde).

3. Fonctionne beaucoup mieux que RDP dans des conditions de faible bande passante, même lorsque vous partagez du contenu à mouvement élevé, tel que des graphiques 3D.
    
N’oubliez pas que ces chiffres reposent sur l’état d’santé et l’optimisation des performances de votre réseau, et peuvent impliquer des réseaux externes au vôtre, si vos clients sont sur des appareils mobiles.
  
Vous devez également être conscient que la fiabilité, la vitesse et l’efficacité ont été les valeurs de fidélité/netteté de votre contenu partagé. Dans la plupart des cas, cela ne sera pas facilement visible pour les utilisateurs.
  
### <a name="ports-and-protocols"></a>Ports et protocoles

**Ports de serveur requis**

|**Rôle serveur**|**Nom du service**|**Port ou plage de ports**|**Protocol (Protocole)**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|Serveurs frontaux  <br/> |Skype Entreprise Server service de partage d’application  <br/> |5065  <br/> |TCP  <br/> |Utilisé pour les demandes d’écoute SIP entrantes dans le cadre du partage d’application.  <br/> |
|Serveurs frontaux  <br/> |Skype Entreprise Server service de partage d’application  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Plage de ports multimédias utilisée pour le partage d’application.  <br/> |
   
**Ports clients requis**

|**Composant**|**Plage de ports**|**Protocol (Protocole)**|**Notes**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Partage d’application.  <br/> |
   
Si QoS est activé pour les ports multimédias suivants et que VbSS est également activé, au cours d’une conférence qui inclut le partage de bureau du MCU AS, les paramètres de port vidéo affichés en gras ci-dessous sont utilisés pour le trafic de partage d’écran. 
  
> [!IMPORTANT]
> Ces paramètres sont un cas particulier et ces paramètres exacts doivent être utilisés lors de l’implémentation de ces deux fonctionnalités. Cela remplace les autres paramètres recommandés dans la [documentation pour QoS](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos). Pour le partage d’application, vous devrez également spécifier ASMCUSVC.exe dans l’GPO QoS en plus de définir ces valeurs de port. 
  
**Paramètres requis de la QoS/VbSS du serveur d’applications**

|**Propriété**|**Valeur du port**|**Protocol (Protocole)**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planification de la capacité

Chaque serveur frontal exécutant la mise à jour cumulative 2 Skype Entreprise Server 2015 (CU2) ou version ultérieure prend en charge jusqu’à 375 participants pour le partage d’écran à l’aide de RDP (mais seulement 250 par réunion). Cette capacité ne change pas après CU3, lorsque VbSS est introduit et utilisé.
  
Cela étant dit, nous avons effectué des tests de performances et de contrainte dans notre laboratoire, et les mesures suivantes doivent également être prises en compte en ce qui concerne votre propre déploiement (en fonction de l’utilisation, bien entendu).
  
En supposant :
  
- Vous utilisez Skype Entreprise Server CU2 2015 ou une ultérieure dans votre déploiement.
    
- Tous les utilisateurs de votre environnement Skype Entreprise Server ont des résolutions d’écran supérieures à 1920 x 1080.
    
À pleine capacité (comme indiqué ci-dessus, 375 participants au partage d’écran par serveur frontal au total, mais seulement 250 par réunion), votre serveur frontal peut utiliser environ 89 % des 1 Gigabit de carte réseau. Cela est dû au fait que la technologie de partage d’écran existante dans Skype Entreprise Server CU2 (RDP) transmet le contenu à l’écran à la résolution native du PC du présentateur. Ainsi, avec des résolutions d’écran plus élevées, vous rencontrez peut-être déjà des goulots d’étranglement réseau pour le partage d’écran avec Skype Entreprise Server CU2 2015.
  
Pour atténuer ce risque, une ou plusieurs des options suivantes peuvent être utiles :
  
- Mettre à niveau votre serveur frontal d’une carte réseau 1 Gigabit vers une carte Ethernet 10 Gigabits.

- Augmenter le nombre de serveurs frontux pour équilibrer la charge du trafic.

- Limitez la bande passante (vitesse de bit) utilisée pour VbSS et RDP en limitant la bande passante maximale utilisée par les deux canaux.
    
Les chiffres de ce tableau sont influencés par des réseaux individuels et par le contenu partagé. Testez pour établir des lignes de base pour votre ou vos réseaux.
  
|**Contenu 1080p**|**Moyenne RDP**|**RDP Peak**|**Moyenne VbSS**|**Pic VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 Kbits/s  <br/> |12mbps  <br/> |100 Kbits/s  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vidéo  <br/> |5mbps  <br/> |7mbps  <br/> |1,3mbps  <br/> |2,2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Besoins en bande passante réseau pour le trafic multimédia

La bande passante VbSS est :
  
|**Codec vidéo**|**Résolution et proportions**|**Vitesse de bits de charge utile vidéo maximale (Kbits/s)**|**Vitesse de bits de charge utile vidéo minimale (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (Les proportions dépendent de la résolution du moniteur du partageur et ne sont pas toujours de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Prise en charge des clients et des serveurs

Le partage d’écran vidéo nécessite Skype Entreprise Server CU3 2015 ou version ultérieure, et une version actuelle des clients de prise en charge répertoriés dans la comparaison des [fonctionnalités](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing) client mobiles pour la prise en charge de [Skype Entreprise](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) et de réunions. 
  
Il existe des situations dans lesquelles le partage d’écran passe à RDP, comme celles-ci :
  
- Si votre compte est hébergé dans un environnement où l’ASMCU ne répond pas à la build minimale qui prend en charge VbSS.
- Si une personne qui utilise une version antérieure du client Skype Entreprise rejoint votre session, par exemple toute personne utilisant une version de client Windows inférieure à la version 16.0.6330.1000, Skype Entreprise Room System Devices ou Skype Entreprise Mobile Apps. 
- Si un utilisateur partage à partir du Application Web Skype Entreprise.
- Si une personne utilise Skype Entreprise sur Mac et qu’elle n’est pas Skype Entreprise Online ou Skype Entreprise Server 2015 avec la mise à jour cumulative de juillet 2018 (ou version ultérieure).
- Si quelqu’un démarre un programme/Windows partage.
- Si quelqu’un commence à enregistrer la session.
- Si quelqu’un appelle le contrôle d’écran distant pendant la session. 
- Réunions de plus de 250 participants (où VbSS n’est pas pris en charge actuellement).

N’ignorez pas qu’une fois que la session passe à RDP, elle ne revenira pas à VbSS. Là encore, la transition à partir de VbSS est censée être transparente et, espérons-le, ne sera pas facile à détecter dans la plupart des situations.
    
> [!NOTE]
> Il n’est pas pris en charge pour bloquer ou tenter de bloquer la transition de VbSS vers RDP dans Skype Entreprise partage d’écran. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Activation, désactivation et configuration de VbSS

La meilleure chose est qu’une fois que vous avez installé la mise à jour cumulative 3 (CU3) de Skype Entreprise Server 2015 ou une version ultérieure, tous vos utilisateurs seront activés pour VbSS 1-à-1 et multi-parties par défaut. Cela peut être problématique pour vous si vous avez une raison de ne pas activer cette fonctionnalité pour tous vos utilisateurs. Dans ce cas, vous pouvez utiliser ces étapes pour désactiver les utilisateurs (les étapes d’activer les utilisateurs suivent) :
  
### <a name="how-to-disable-users-from-using-vbss"></a>Comment désactiver l’utilisation de VbSS par les utilisateurs

- Vous pouvez affecter une stratégie utilisateur qui n’autorise pas VbSS à tous les utilisateurs qui ne doivent pas utiliser VbSS en exécutant cette cmdlet dans la console de gestion Skype Entreprise (remplacez [PolicyName] par la stratégie pour qui vous exécutez cette commande) :
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale, qui affectera tous les utilisateurs sans stratégie affectée :
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous devez désactiver complètement VbSS, vous pouvez exécuter la commande ci-après :
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Pour plus d’informations sur cette commande, [voir Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans une réunion à plusieurs Skype Entreprise, tous les points de terminaison clients respectent le paramètre de stratégie pour l’organisateur de la réunion. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Comment permettre aux utilisateurs d’utiliser VbSS

- Vous pouvez affecter une stratégie utilisateur spécifique qui autorise VbSS à tous les utilisateurs qui doivent utiliser VbSS en exécutant cette cmdlet dans la console de gestion Skype Entreprise (remplacez [PolicyName] par la stratégie pour qui vous exécutez cette commande) :
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Vous pouvez également mettre à jour la stratégie de conférence globale, qui affectera tous les utilisateurs sans stratégie affectée :
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Pour plus d’informations sur cette commande, voir [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Si vous devez remettre VbSS sur le service après l’avoir éteint (c’est le cas par défaut), vous pouvez exécuter la commande ci-après :
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Pour plus d’informations sur cette commande, [voir Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Dans une réunion à plusieurs Skype Entreprise, tous les points de terminaison clients respectent le paramètre de stratégie pour l’organisateur de la réunion. 
  
## <a name="see-also"></a>Voir aussi

[Skype Entreprise Server cumulative 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[Le partage d’écran vidéo (VBSS) est disponible Skype Entreprise Server 2015](https://support.microsoft.com/kb/3170163)