---
title: Planification de serveur interopérabilité vidéo dans Skype Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Résumé : Passez en revue cette rubrique lors de la planification intégrer Skype pour Business Server avec les périphériques de téléconférence tiers.'
ms.openlocfilehash: 015f93496879e84c1959db7d6b46b765e0d286e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213516"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planification de serveur interopérabilité vidéo dans Skype Business Server
 
**Résumé :** Consulter cette rubrique lors de la planification intégrer Skype pour Business Server avec les périphériques de téléconférence tiers.
  
Skype pour Business Server vous permet maintenant d’intégrer avec certaines solutions VTC (système de téléconférence vidéo) tiers. Le nouveau rôle de serveur qui permet l’interopérabilité de cette conférence vidéo est vidéo Interop Server (pouces), qui est actuellement implémentée en tant qu’un rôle de serveur autonome qui est disponible uniquement pour les installations locales. Un rapport joue le rôle d’intermédiaire entre un système de téléconférence tiers et un Skype pour le déploiement de serveur d’entreprise. Pour cette version, le VIS se concentre sur l’interopérabilité avec les systèmes vidéo Cisco/Tandberg. Lisez cet article pour déterminer s’il faut utiliser cette fonctionnalité dans votre Skype pour l’installation du serveur d’entreprise.
  
## <a name="device-interoperability"></a>Interopérabilité des dispositifs

Interopérabilité est testée et prise en charge avec Cisco VTCs inscription avec Cisco Unified Communications Manager (CallManager ou CUCM) version 10.5 et les jonctions SIP TCP configuré entre CUCM et la vis
  
Les VTC actuellement pris en charge sont :
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  Logiciel Cisco version TC7.0.0 ou supérieur est requis sur ces systèmes pour l’intégration avec Skype pour Business Server fonctionnent comme prévu.
  
## <a name="sip-trunks"></a>Jonctions SIP

Les fonctions vidéo Interop serveur en mode de jonction SIP, où les VTCs continuent à inscrire auprès de l’infrastructure Cisco - par exemple, Cisco appeler Manager (CUCM). Un tronçon SIP vidéo est défini entre CUCM et le VIS de manière à acheminer les appels entre les deux systèmes. Seuls les appels via le tronçon SIP entre le VTC et le VIS sont pris en charge. Par conséquent, VTCs puissent se connecter à un Skype pour conférence Business (par composer le numéro de téléphone associé avec le standard automatique des appels), mais ne peut pas être glisser-déplacer dans la conférence.
  
![Diagramme de VIS dans Skype Entreprise](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Fonctionnalités

Ce rôle serveur fournit :
  
- Conversion entre les formats H.264 utilisé par les systèmes vidéo 3ème partie et le Skype pour le déploiement Business Server.
    
- Conversion d’un seul flux vidéo à une résolution donnée à partir d’un VTC en plusieurs flux de diffusion simultanée de différentes résolutions pour une utilisation dans le Skype pour le déploiement de serveur d’entreprise. Ces flux peut être envoyé vers le AVMCU, puis vers Skype pour les points de terminaison Business Server et d’autres systèmes vidéo que vous ont demandé à différentes résolutions. Cette conversion est également utilisée lorsque le système vidéo tiers est impliqué dans un Skype pour les entreprises A / V téléconférence appeler. Une fois que la limite de transcodage est atteinte dans un serveur VIS particulier, toutes les requêtes suivantes pour différentes résolutions reçoit un flux de données avec la plus faible résolution. 
    
- Prise en charge pour une jonction SIP vidéo entre la passerelle CUCM et un Skype pour Business vidéo Interop Server ; VTCs continuer à enregistrer avec la passerelle Cisco et lancer des appels vers le Skype pour le déploiement d’entreprise par le biais de la passerelle. Appels sont routés à partir de la passerelle vers la Skype pour serveur interopérabilité vidéo professionnels sur la jonction SIP vidéo.
    
- Prise en charge pour un utilisateur dans une salle de conférence avec un système vidéo prises en charge de la numérotation à partir de ce système pour participer à une conférence ouverte ou fermée. Cet appel sera parcourir la jonction SIP vidéo.
    
- Prise en charge pour un utilisateur dans une salle de conférence avec un système vidéo prises en charge appeler un Skype pour client d’entreprise. L’appel parcourt la jonction SIP.
    
- Prise en charge pour le contrôle d’appel intermédiaire à partir de la Skype côté serveur de l’entreprise ou à partir du système VTC pris en charge pour les appels point à point et multipoints, y compris audio muet/non-sélectionné-mute, suspendre/reprendre la vidéo, vidéo de verrouillage et d’appels en attente/Annuler-attente.
    
## <a name="known-limitations"></a>Limitations connues

Ce rôle serveur présente les limitations suivantes :
  
- Nouveaux appels à partir de la Skype pour le déploiement d’entreprise à le VTCs via la jonction SIP vidéo ne sont pas pris en charge. . Cela signifie que seuls les appels nouvelles à partir des VTCs dans le Skype pour le déploiement d’entreprise sont pris en charge sur la jonction SIP vidéo. La présence pour le système vidéo pris en charge ne seront pas disponible via la jonction SIP vidéo à la vis 
    
- Seul un pool VIS autonome est pris en charge en mode tronçon SIP vidéo.
    
-  TLS + SRTP ou TCP + RTP est pris en charge pour les communications entre le VTC et le VIS via le tronçon SIP vidéo.
    
- Le partage d’applications n’est pas pris en charge. Un Skype pour l’utilisateur d’entreprise dans la salle de conférence doit participer à la Skype pour conférence Business (via un ordinateur portable par exemple) et affiche l’application partage écrans sur un des moniteurs libres dans la salle de conférence n’est ne pas associé à le VTC.
    
- La capacité d’un VTC à rejoindre une réunion fédérée via le VIS n’est pas prise en charge.
    
- La capacité d’un VTC à rejoindre une réunion en ligne via le VIS n’est pas prise en charge.
    
- Les appels d’un VTC à un réseau RTC via le VIS ne sont pas pris en charge.
    
- Les appels du réseau RTC à un VTC via le VIS ne sont pas pris en charge.
    
## <a name="resiliency-mechanisms"></a>Mécanismes de résilience
<a name="resiliency"> </a>

Le VIS prend en charge les appels entrants d’un CUCM transitant par un tronçon SIP vidéo. Une perte de connectivité en amont ou en aval étant possible, vous devez envisager les deux possibilités suivantes pour profiter d’une résilience robuste :
  
1. **Basculement de Pool VIS** Si le pool principal VIS vers la passerelle vidéo vers le bas, la récupération est possible si la passerelle vidéo a défini des jonctions vers des pools de VIS deux (ou plus). Si la passerelle vidéo détermine qu’elle ne peut pas passer les appels vers le pool VIS principal, elle achemine simplement les appels vers le pool VIS secondaire.
    
     ![Schéma de basculement de pool du service d’interopérabilité vidéo (VIS)](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un pool VIS particulier peut avoir des jonctions à plusieurs passerelles, mais généralement une passerelle donnée ne peut avoir de jonctions à plusieurs pools VIS, un pli doit être effectuée pour prendre en charge ce basculement : définir 2 FDQNs dans DNS qui acheminer vers la même adresse IP d’une passerelle de vidéo. Représentent chaque nom de domaine complet sous la forme d’une passerelle séparée vidéo dans le Document de topologie dans laquelle chaque passerelle vidéo a une jonction vers un autre pool VIS, et la récupération est désormais possible. (Si TLS est utilisé, les différents noms vous devrez être SAN du certificat passerelle vidéo.)
    
    > [!NOTE]
    > Le VIS autorise uniquement les appels entrants provenant des passerelles configurées dans le document de topologie. 
  
2. **Basculement frontal** Si un pool VIS reçoit un appel CUCM, mais ne peut pas joindre son pool de serveurs d’inscriptions ou Front-End principal tronçon suivant, les appels sont routés vers un pool frontal de sauvegarde.
    
     ![Schéma de basculement frontal](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    Le rapport est suivi de l’état de son pool frontal principal et son pool frontal sauvegarde (le paramètre se trouve dans le paramètre de sauvegarde pour le service serveur d’inscriptions dans le Document de topologie). Il envoie des sondages Options une fois par minute à deux pools, et s’il y a cinq tentatives infructueuses la VIS suppose qu’un pool frontal particulier est inactif. Si le pool frontal principal est marqué comme vers le bas et il est configuré disponible sauvegarde la VIS envoie nouveaux appels depuis la passerelle vers le pool frontal de sauvegarde. Une fois que le pool frontal principal revient, le rapport reprend à l’aide du pool frontal principal pour les nouveaux appels.
    
    Le VIS implémente également un minuteur de 10 secondes pour les appels qui proviennent du tronçon SIP vidéo. Si le pool frontal de tronçon suivant principal a été utilisé pour un appel à partir de la jonction SIP vidéo et le serveur frontal tronçon suivant principal pool ne répond pas à l’invitation qui lui sont envoyée au sein de cette valeur du minuteur, la sauvegarde proxy de tronçon suivant pour l’appel s avec un message SIP (y compris Trying 100) hould tentée si configuré. 
    
    > [!NOTE]
    > Si le système de secours est utilisé en premier, aucune tentative ne sera exécutée sur le système principal. 
  
    L’administrateur peut également utiliser la commande de basculement de Windows PowerShell pour forcer le VIS à utiliser le pool frontal de secours, par exemple, lorsqu’une maintenance doit être exécutée sur le pool frontal principal.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistence de tronçons audio et vidéo sur le même homologue de passerelle
<a name="resiliency"> </a>

Skype pour Business Server gère la voix et vidéo jonctions SIP utilisent le même homologue de passerelle. C’est pourquoi le même déploiement CUCM peut comprendre des tronçons SIP audio sur le serveur de médiation et des tronçons SIP vidéo sur le VIS.
  
- Il est nécessaire de définir une passerelle PSTN avec un nom de domaine complet particulier dans le document de topologie pour les tronçons SIP audio.
    
- L’homologue de la passerelle PSTN est le serveur de médiation.
    
- Il est possible de définir plusieurs tronçons audio répartis entre une passerelle PSTN et plusieurs pools de serveur de médiation, si nécessaire.
    
- Une passerelle vidéo doit être définie dans le document de topologie pour le tronçon SIP vidéo possédant le même nom de domaine complet que la passerelle PSTN.
    
- L’homologue de la passerelle vidéo est le VIS.
    
- Il est possible de ne définir qu’un seul tronçon vidéo entre une passerelle vidéo et un pool VIS particulier.
    
- CUCM doit être configuré pour acheminer correctement les appels via le tronçon audio et le tronçon vidéo. Par exemple, vous pouvez utiliser un préfixe de numérotation spécial lors de la numérotation à partir du VTC ; CUCM peut associer ce préfixe aux appels du VIS et appliquer les règles de conversion appropriées entre SIP Invite et le VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistence de VIS dans Skype Entreprise avec les versions précédentes de Lync
<a name="resiliency"> </a>

VIS ne peut être déployée dans le cadre de Skype pour le déploiement d’entreprise. Il peut interagir avec des conférences Lync 2013 et les clients qui font partie d’un déploiement existant ; Dans ce cas, le pool VIS vous devrez faire partie d’un Skype pour le déploiement d’entreprise qui inclut un pool de serveurs d’inscriptions/FE est le tronçon suivant pour le pool VIS.
  
Le VIS ne prend pas en charge le transcodage entre RTV et H.264. Il n’existe pas d’interopérabilité entre les clients pré-Lync 2013 et les participants VTC dans une conférence.
  
La présence de clients pré-Lync 2013 dans une conférence contraint les clients mobiles à utiliser RTV pour les transmissions. Le cas échéant, les VTC ne reçoivent pas de vidéo lorsque le client mobile passe en mode de présentateur principal.
  
Pour que Lync 2013 fonctionne correctement avec le VIS dans le cadre d’un déploiement de Skype Entreprise, Lync 2013 requiert l’application des mises à jour cumulées appropriées afin de mettre à niveau le client Lync 2013, le CAA, et l’AVMCU afin qu’ils fonctionnent avec le VIS.
  
L’interopérabilité du VIS avec les clients Lync 2013 et Skype Entreprise (version ordinateur de bureau) a été testée et est prise en charge.
  
Interopérabilité de VIS avec les postes de travail (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype pour les clients professionnels disponibles à partir du magasin d’applications applicables au moment de la version VIS a été testée et est pris en charge.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Récupération de la perte de paquets via la correction des erreurs de transfert (FEC)
<a name="resiliency"> </a>

Vous pouvez activer la FEC pour faciliter la récupération des pertes de paquets. Lorsqu’elle est activée, les transmissions entre le VIS et le VTC utilisent 50 % de bande passante en plus.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Taille du VIS et coûts de transcodage
<a name="resiliency"> </a>

Transcoder les flux vidéo simples entre le VTC de Cisco et plusieurs flux simulcast consomme des ressources processeur. Environ 16 VTCs peuvent avoir leur transcodage vidéo (en supposant qu’un flux vidéo 720 pixels de chaque VTC est converti en 3 flux de diffusion simultanée distincte à 720 pixels, p 360 et 180p) dans un rapport unique en cours d’exécution sur l’équivalent de la plateforme FE recommandé de Lync 2013. Si le transcodage est désactivé, vous économisez les ressources du processeur du VIS. Cependant, l’image vidéo que le VIS demande au VTC sera d’une résolution standard inférieure pour satisfaire tous les destinataires côté Skype Entreprise. Notez que même si le transcodage est désactivé, il est possible de l’activer lorsque des clients Skype Entreprise exigent certaines basses résolutions non prise en charge par les VTC.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribution des appels de la passerelle vidéo vers le VIS
<a name="resiliency"> </a>

La distribution est réalisée via l’un des mécanismes de distribution CUCM suivants :
  
- Dynamiquement à l’aide de DNS.
    
- Côté CUCM, vous pouvez définir des tronçons individuels, chaque tronçon étant relié à un serveur différent dans le pool VIS. CUCM achemine les appels sur les différents tronçons.
    
## <a name="no-hybrid-interoperability"></a>Absence d’interopérabilité hybride
<a name="resiliency"> </a>

La prise en charge des VTC permettant de rejoindre des réunions en ligne via le VIS installé dans les locaux n’est pas intégrée à Skype Entreprise.
  
## <a name="no-federation-support"></a>Aucune prise en charge fédérée
<a name="resiliency"> </a>

La prise en charge des VTC permettant de rejoindre des réunions fédérées via le VIS n’est pas intégrée à Skype Entreprise.
  
## <a name="see-also"></a>Voir aussi
<a name="resiliency"> </a>

[Déployer le serveur interopérabilité vidéo dans Skype pour Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
