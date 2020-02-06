---
title: Planifier le serveur Video Interop dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Résumé : reportez-vous à cette rubrique pour planifier l’intégration de Skype entreprise Server à des appareils de téléconférence tiers.'
ms.openlocfilehash: af7618efa0b5f13419be216b37a4f1e7d4065e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815562"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planifier le serveur Video Interop dans Skype entreprise Server
 
**Résumé :** Consultez cette rubrique lors de la planification de l’intégration de Skype entreprise Server à des appareils de téléconférence tiers.
  
Skype entreprise Server vous permet désormais de procéder à l’intégration à certaines solutions de VTC (Video Teleconferencing System) tierces. Le nouveau rôle de serveur qui permet cette interopérabilité des conférences vidéo est le serveur d’interopérabilité vidéo (qui est actuellement implémenté en tant que rôle serveur autonome disponible uniquement pour les installations locales). A fait office de intermédiaire entre un système de téléconférence tiers et un déploiement Skype entreprise Server. Pour cette version, le VIS se concentre sur l’interopérabilité avec les systèmes vidéo Cisco/Tandberg. Consultez cet article pour déterminer si vous souhaitez utiliser cette fonctionnalité dans votre installation de Skype entreprise Server.
  
## <a name="device-interoperability"></a>Interopérabilité des dispositifs

L’interopérabilité est testé et pris en charge par Cisco VTCs Register with Cisco Unified Communications Manager (CallManager, ou CUCM) version 10,5 et les Trunks SIP TCP sont configurés entre CUCM et la fonction.
  
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
>  Le logiciel Cisco version TC 7.0.0 ou version ultérieure est requis sur ces systèmes pour une intégration avec Skype entreprise Server.
  
## <a name="sip-trunks"></a>Jonctions SIP

Le serveur vidéoconférence fonctionne en mode Trunk SIP, dans lequel VTCs continue de s’inscrire auprès de l’infrastructure Cisco actuelle (par exemple, le gestionnaire d’appels Cisco (CUCM). Un tronçon SIP vidéo est défini entre CUCM et le VIS de manière à acheminer les appels entre les deux systèmes. Seuls les appels via le tronçon SIP entre le VTC et le VIS sont pris en charge. Par conséquent, VTCs peut appeler une conférence Skype entreprise (en composant le numéro de téléphone associé au standard automatique d’appel), mais ne peut pas être glissé et déposé dans la Conférence.
  
![Diagramme de VIS dans Skype Entreprise](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Fonctionnalités

Ce rôle serveur fournit :
  
- Conversion entre les formats H. 264 utilisés par des systèmes vidéo tiers et le déploiement de Skype entreprise Server.
    
- Conversion d’un flux vidéo unique à une résolution donnée à partir d’un VTC en plusieurs flux simultanés de résolutions différentes pour une utilisation dans le déploiement de Skype entreprise Server. Ces flux peuvent être envoyés au AVMCU, puis aux points de terminaison Skype entreprise Server et autres systèmes vidéo ayant demandé des résolutions différentes. Cette conversion est également utilisée lorsque le système vidéo tiers est impliqué dans une téléconférence A/V Skype entreprise. Dès lors que la limite de transcodage est atteinte dans un serveur particulier, toutes les demandes suivantes pour différentes résolutions ne recevront qu’un flux avec la résolution la plus basse. 
    
- Prise en charge d’un Trunk SIP vidéo entre la passerelle CUCM et un serveur vidéo interopérabilité Skype entreprise Server. VTCs continuent de s’inscrire auprès de la passerelle Cisco et de lancer des appels de déploiement Skype entreprise par le biais de la passerelle. Les appels sont routés de la passerelle vers le serveur vidéo Interop Skype entreprise via le Trunk SIP vidéo.
    
- La prise en charge d’un utilisateur dans une salle de conférence avec un système vidéo compatible pour composer le numéro à partir de ce système pour participer à une conférence ouverte ou fermée. Cet appel va traverser la ligne SIP Video Trunk.
    
- La prise en charge d’un utilisateur dans une salle de conférence avec un système vidéo compatible pour appeler un client Skype entreprise. L’appel traverse le Trunk SIP.
    
- Prise en charge du contrôle d’appel de milieu de gamme du serveur Skype entreprise ou du système VTC pris en charge pour les appels point à point et multipoint, y compris le son muet, l’interruption/la reprise vidéo, le verrouillage de la vidéo et la mise en attente d’un appel.
    
## <a name="known-limitations"></a>Limitations connues

Ce rôle serveur présente les limitations suivantes :
  
- Les nouveaux appels du déploiement de Skype entreprise vers le VTCs via le protocole SIP vidéo ne sont pas pris en charge. . Cela signifie que seuls les nouveaux appels du VTCs dans le déploiement de Skype entreprise sont pris en charge sur le Trunk SIP vidéo. La présence du système vidéo compatible ne sera pas disponible sur la ligne SIP vidéo. 
    
- Seul un pool VIS autonome est pris en charge en mode tronçon SIP vidéo.
    
-  TLS + SRTP ou TCP + RTP est pris en charge pour les communications entre le VTC et le VIS via le tronçon SIP vidéo.
    
- Le partage d’applications n’est pas pris en charge. Un utilisateur de Skype entreprise dans la salle de conférence doit rejoindre la Conférence Skype entreprise (par exemple, sur un ordinateur portable) et afficher les écrans de partage d’application sur l’un des écrans gratuits de la salle de conférence non associé à VTC.
    
- La capacité d’un VTC à rejoindre une réunion fédérée via le VIS n’est pas prise en charge.
    
- La capacité d’un VTC à rejoindre une réunion en ligne via le VIS n’est pas prise en charge.
    
- Les appels d’un VTC à un réseau RTC via le VIS ne sont pas pris en charge.
    
- Les appels du réseau RTC à un VTC via le VIS ne sont pas pris en charge.
    
## <a name="resiliency-mechanisms"></a>Mécanismes de résilience
<a name="resiliency"> </a>

Le VIS prend en charge les appels entrants d’un CUCM transitant par un tronçon SIP vidéo. Une perte de connectivité en amont ou en aval étant possible, vous devez envisager les deux possibilités suivantes pour profiter d’une résilience robuste :
  
1. En vertu du **basculement de pool** Si le regroupement principal qui pointe vers le bas de la passerelle vidéo est arrêté, la récupération est possible si la passerelle vidéo a défini des Trunks vers deux (ou plus). Si la passerelle vidéo détermine qu’elle ne peut pas passer les appels vers le pool VIS principal, elle achemine simplement les appels vers le pool VIS secondaire.
    
     ![Schéma de basculement de pool du service d’interopérabilité vidéo (VIS)](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un pool particulier peut avoir des Trunks vers plusieurs passerelles, mais en règle générale, une passerelle particulière ne peut pas avoir de Trunks vers plusieurs réserves, de sorte qu’une astuce doit être exécutée pour prendre en charge ce basculement : définissez 2 FDQNs dans le DNS qui est résolu vers la même adresse IP d’une passerelle vidéo. Représenter chaque nom de domaine complet comme passerelle vidéo séparée dans le document topologique dans lequel chaque passerelle vidéo dispose d’un Trunk vers un pool d’objets différent et la récupération est désormais possible. (Si TLS est utilisé, les noms multiples doivent figurer dans le SAN du certificat de passerelle vidéo.)
    
    > [!NOTE]
    > Le VIS autorise uniquement les appels entrants provenant des passerelles configurées dans le document de topologie. 
  
2. **Basculement frontal** Si un groupe d’utilisateurs a reçu un appel de CUCM mais qu’il ne peut pas accéder à son bureau d’enregistrement principal ou au pool frontal principal, les appels sont routés vers un pool frontal de sauvegarde.
    
     ![Schéma de basculement frontal](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    L’option garde le suivi de l’état de son pool frontal principal et de sa réserve frontale de sauvegarde (le paramètre est disponible dans le paramètre de sauvegarde du service d’inscription figurant dans le document topologique). Ce service envoie des options d’interrogation une fois par minute aux deux pools, et s’il y a cinq échecs consécutifs, le présupposé qu’un pool frontal particulier est arrêté. Si le pool frontal principal est marqué comme étant arrêté et qu’il n’y a pas de sauvegarde configurée, l’option à envoie de nouveaux appels de la passerelle vers le pool frontal de sauvegarde. Lorsque le pool principal principal est en retour, le feu d’activation reprend le regroupement principal frontal pour les nouveaux appels.
    
    Le VIS implémente également un minuteur de 10 secondes pour les appels qui proviennent du tronçon SIP vidéo. Si le pool principal de sauts principal a été utilisé pour un appel à partir du Trunk vidéo SIP et si le pool frontal principal de sauts de ligne n’a pas répondu à un message SIP (y compris 100 essayant) de l’invitation qui lui est envoyée dans le cadre de cette valeur du minuteur, le proxy du tronçon Hould être essayé si configuré. 
    
    > [!NOTE]
    > Si le système de secours est utilisé en premier, aucune tentative ne sera exécutée sur le système principal. 
  
    L’administrateur peut également utiliser la commande de basculement de Windows PowerShell pour forcer le VIS à utiliser le pool frontal de secours, par exemple, lorsqu’une maintenance doit être exécutée sur le pool frontal principal.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistence de tronçons audio et vidéo sur le même homologue de passerelle
<a name="resiliency"> </a>

Skype entreprise Server prend en charge l’utilisation du même homologue de passerelle pour les lignes SIP audio et vidéo. C’est pourquoi le même déploiement CUCM peut comprendre des tronçons SIP audio sur le serveur de médiation et des tronçons SIP vidéo sur le VIS.
  
- Il est nécessaire de définir une passerelle PSTN avec un nom de domaine complet particulier dans le document de topologie pour les tronçons SIP audio.
    
- L’homologue de la passerelle PSTN est le serveur de médiation.
    
- Il est possible de définir plusieurs tronçons audio répartis entre une passerelle PSTN et plusieurs pools de serveur de médiation, si nécessaire.
    
- Une passerelle vidéo doit être définie dans le document de topologie pour le tronçon SIP vidéo possédant le même nom de domaine complet que la passerelle PSTN.
    
- L’homologue de la passerelle vidéo est le VIS.
    
- Il est possible de ne définir qu’un seul tronçon vidéo entre une passerelle vidéo et un pool VIS particulier.
    
- CUCM doit être configuré pour acheminer correctement les appels via le tronçon audio et le tronçon vidéo. Par exemple, vous pouvez utiliser un préfixe de numérotation spécial lors de la numérotation à partir du VTC ; CUCM peut associer ce préfixe aux appels du VIS et appliquer les règles de conversion appropriées entre SIP Invite et le VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistence de VIS dans Skype Entreprise avec les versions précédentes de Lync
<a name="resiliency"> </a>

Ne peut être déployée que dans le cadre du déploiement de Skype entreprise. Il peut interagir avec des conférences et clients Lync 2013 qui font partie d’un déploiement existant ; dans ces cas-là, le regroupement doit faire partie d’un déploiement Skype entreprise incluant un pool d’inscriptions/FE qui est le tronçon suivant pour le pool d’utilisateurs.
  
Le VIS ne prend pas en charge le transcodage entre RTV et H.264. Il n’existe pas d’interopérabilité entre les clients pré-Lync 2013 et les participants VTC dans une conférence.
  
La présence de clients pré-Lync 2013 dans une conférence contraint les clients mobiles à utiliser RTV pour les transmissions. Le cas échéant, les VTC ne reçoivent pas de vidéo lorsque le client mobile passe en mode de présentateur principal.
  
Pour que Lync 2013 fonctionne correctement avec le VIS dans le cadre d’un déploiement de Skype Entreprise, Lync 2013 requiert l’application des mises à jour cumulées appropriées afin de mettre à niveau le client Lync 2013, le CAA, et l’AVMCU afin qu’ils fonctionnent avec le VIS.
  
L’interopérabilité du VIS avec les clients Lync 2013 et Skype Entreprise (version ordinateur de bureau) a été testée et est prise en charge.
  
Interopérabilité de à l’aide de la version non-ordinateur de bureau (Android, iPad, iPhone, Windows Phone, LMX, etc.) Les clients Skype entreprise disponibles sur le magasin d’applications en vigueur au moment de la publication et sont pris en charge.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Récupération de la perte de paquets via la correction des erreurs de transfert (FEC)
<a name="resiliency"> </a>

Vous pouvez activer la FEC pour faciliter la récupération des pertes de paquets. Lorsqu’elle est activée, les transmissions entre le VIS et le VTC utilisent 50 % de bande passante en plus.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Taille du VIS et coûts de transcodage
<a name="resiliency"> </a>

Transcoder les flux vidéo simples entre le VTC de Cisco et plusieurs flux simulcast consomme des ressources processeur. Environ 16 VTCs peuvent avoir leur transcodage vidéo (en partant du principe qu’un flux vidéo 720p de chaque VTC est transcodé en 3 flux simultanés distincts sur 720p, 360p et 180p) en une seule et même exécution sur l’équivalent de la plateforme FE de Lync 2013. Si le transcodage est désactivé, vous économisez les ressources du processeur du VIS. Cependant, l’image vidéo que le VIS demande au VTC sera d’une résolution standard inférieure pour satisfaire tous les destinataires côté Skype Entreprise. Notez que même si le transcodage est désactivé, il est possible de l’activer lorsque des clients Skype Entreprise exigent certaines basses résolutions non prise en charge par les VTC.
  
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

[Déploiement d’un serveur de technologie d’interopérabilité vidéo dans Skype entreprise Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
