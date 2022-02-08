---
title: Rapport détaillé des appels dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Résumé : Découvrez le rapport détaillé des appels utilisé dans Skype Entreprise Server.'
ms.openlocfilehash: d6d8a79506e215bd46a54c89969fc5991f9962d6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385616"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Rapport détaillé des appels dans Skype Entreprise Server
 
**Résumé :** Découvrez le rapport détaillé de l’appel utilisé dans Skype Entreprise Server.
  
Le rapport détaillé de l’appel fournit une analyse détaillée d’un appel individuel . Le rapport inclut presque toutes les mesures et statistiques de qualité de l’expérience collectées par Skype Entreprise Server, divisées en sections de rapport telles que :
  
- Informations d’appel 
    
- Mesures du signal et du périphérique de l’appelant
    
- Mesures du signal et du périphérique de l’appelé
    
- Événement client de l’appelant
    
- Événement client de l’appelé
    
- Flux de données audio (de l’appelant vers l’appelé)
    
- Flux de données vidéo (de l’appelant vers l’appelé)
    
- Flux de données audio (de l’appelé vers l’appelant)
    
- Flux de données vidéo (de l’appelé vers l’appelant)
    
Gardez à l’esprit que les catégories et les mesures qui figurent dans un rapport donné dépendent de deux facteurs : du type de session et du type des systèmes d’extrémité utilisés dans la session. Par exemple, un appel audio ne fait l’objet d’aucune mesure de flux de données vidéo, car il n’en comporte pas. De même, il peut arriver qu’un rapport répertorie des statistiques sur l’appelant mais pas sur l’appelé. En règle générale, cela est dû au fait que l’appelé utilise un appareil non compatible SIP. La génération de statistiques à la fin d’un appel est une tâche qui incombe aux systèmes d’extrémité. Or, un téléphone cellulaire (qui n’a pas connaissance de SIP ni des statistiques SIP) n’est pas capable de fournir ce type d’information. Si vous appelez une personne et qu’elle vous répond sur son téléphone cellulaire, vous n’obtiendrez pas de rapport de ce téléphone à la fin de l’appel.
  
Le rapport sur le détail de l’appel s’avère particulièrement utile pour identifier les causes exactes des problèmes de qualité des médias rencontrés lors d’un appel donné.
  
## <a name="accessing-the-call-detail-report"></a>Accès au rapport sur le détail de l’appel

Le rapport sur le détail de l’appel est accessible à partir des rapports suivants :
  
- [Rapport d’emplacement dans Skype Entreprise Server (location-report.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres)
    
- [Media Quality Summary Report in Skype Entreprise Server (summary.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres)
    
- Le [rapport comparatif de la qualité des médias Skype Entreprise Server](comparison.md) (en cliquant sur le rapport de liste d’appels [dans Skype Entreprise Server](call-list-report-0.md) puis sur la mesure Détail).
    
- Rapport [sur les performances du serveur Skype Entreprise Server](server-performance.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres)
    
- Rapport [de liste d’appels Skype Entreprise Server](call-list-report-0.md) (en cliquant sur la mesure Détail)
    
À partir du rapport détaillé des appels, vous pouvez accéder au rapport de périphérique dans [Skype Entreprise Server](device-report.md) en cliquant sur l’une des mesures suivantes :
  
- Périphérique de capture
    
- Périphérique de rendu
    
Vous pouvez aussi accéder au Rapport de tendance générale de la qualité des médias serveur en cliquant sur la mesure Serveur Edge A/V.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Utilisation optimale du rapport sur le détail de l’appel

En règle générale, le rapport sur le détail de l’appel comprend plus de 250 mesures différentes, avec notamment les éléments Dérive d’horodatage du microphone, Durée du SNR faible et Durée de l’écho au point de terminaison. Si vous ne vous rappelez pas de la fonction de l’une de ces nombreuses mesures, placez le curseur de la souris sur l’étiquette de la mesure ; vous devriez obtenir une info-bulle décrivant cette mesure.
  
Si vous avez des difficultés à trouver une mesure, tapez une partie de l’étiquette de mesure dans la zone de recherche, puis cliquez sur **Rechercher**. Par exemple, si vous ne trouvez pas la mesure Durée du SNR faible, tapez SNR dans la zone de recherche, puis cliquez sur **Rechercher**.
  
Notez que le rapport suit uniquement les informations sur un appel. L’appel proprement dit n’est pas enregistré.
  
## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer le rapport sur le détail de l’appel.
  
## <a name="metrics"></a>Mesures

Le tableau suivant liste les informations fournies dans le rapport sur le détail de l’appel pour chaque appel.
  
**Mesures du rapport sur le détail de l’appel**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**PAI de l’appelant** <br/> |Non  <br/> |PAI (P-Asserted-Identity) de l’utilisateur qui a initié l’appel. La PAI sert à transmettre l’identité prouvée d’un utilisateur au sein d’un réseau approuvé.  <br/> |
|**URI de l’appelant** <br/> |Non  <br/> |Adresse SIP de l’utilisateur qui a initié l’appel.  <br/> |
|**Système d’extrémité de l’appelant** <br/> |Non  <br/> |Appareil utilisé pour passer l’appel.  <br/> |
|**Agent utilisateur de l’appelant** <br/> |Non  <br/> |Logiciel utilisé sur l’appareil utilisé pour passer l’appel.  <br/> |
|**Début de l’appel** <br/> |Non  <br/> |Date et heure où l’appel a été passé.  <br/> |
|**Appel de contournement du serveur de médiation** <br/> |Non  <br/> |Indique si l’appel connecté à une passerelle vocale PSTN ou IP-PBX qualifié sans passer par le serveur de médiation.  <br/> |
|**SE de l’appelant** <br/> |Non  <br/> |Système d’exploitation de l’ordinateur de l’appelant.  <br/> |
|**UC de l’appelant** <br/> |Non  <br/> |UC installée dans l’ordinateur de l’utilisateur qui a passé l’appel.  <br/> |
|**Numéro principal de l’UC de l’appelant** <br/> |Non  <br/> |Numéro de processeur dans l’ordinateur utilisé par la personne qui a passé l’appel.  <br/> |
|**Vitesse de l’UC de l’appelant** <br/> |Non  <br/> |Vitesse d’horloge de l’UC de l’ordinateur utilisé par la personne qui a initié l’appel.  <br/> |
|**Virtualisation de l’UC de l’appelant** <br/> |Non  <br/> |Virtualisation (le cas échéant) utilisée sur l’ordinateur utilisé par la personne qui a initié l’appel.  <br/> |
|**PAI de l’appelé** <br/> |Non  <br/> |PAI (P-Asserted-Identity) de l’utilisateur qui a été invité à participer à l’appel. La PAI sert à transmettre l’identité prouvée d’un utilisateur au sein d’un réseau approuvé.  <br/> |
|**URI de l’appelé** <br/> |Non  <br/> |Adresse SIP de l’utilisateur appelé.  <br/> |
|**Système d’extrémité de l’appelé** <br/> |Non  <br/> |Appareil utilisé pour recevoir l’appel.  <br/> |
|**Agent utilisateur de l’appelé** <br/> |Non  <br/> |Logiciel utilisé sur l’appareil qui a reçu l’appel.  <br/> |
|**Duration** <br/> |Non  <br/> |Durée de l’appel.  <br/> |
|**Indicateur d’avertissement de contournement de média** <br/> |Non  <br/> |Avertissement paru quand le serveur de médiation a été contourné.  <br/> |
|**SE de l’appelé** <br/> |Non  <br/> |Système d’exploitation de l’ordinateur de l’appelé.  <br/> |
|**UC de l’appelé** <br/> |Non  <br/> |UC installée dans l’ordinateur de l’utilisateur qui a été appelé.  <br/> |
|**Numéro principal de l’UC de l’appelé** <br/> |Non  <br/> |Numéro de processeur dans l’ordinateur utilisé par la personne qui a été appelée.  <br/> |
|**Vitesse de l’UC de l’appelé** <br/> |Non  <br/> |Vitesse d’horloge de l’UC de l’ordinateur utilisé par la personne qui a été appelée.  <br/> |
|**Virtualisation de l’UC de l’appelé** <br/> |Non  <br/> |Virtualisation (le cas échéant) utilisée sur l’ordinateur utilisé par la personne qui a été appelée.  <br/> |
   

