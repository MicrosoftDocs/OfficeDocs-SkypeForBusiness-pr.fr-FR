---
title: Calculateur de planification de la capacité Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Résumé : comment utiliser l’outil calculateur de capacité.'
ms.openlocfilehash: 24e268c6ecc3cc48fbfb4405f1e5e6b008639944
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274456"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculateur de planification de la capacité Skype Entreprise Server
 
**Résumé :** comment utiliser l’outil calculateur de capacité.

> [!NOTE]
> Cet article fait référence aux téléchargements Skype entreprise Server 2015, mais s’applique à:
> - Skype entreprise Server 2019.
> - Skype entreprise Server 2015.
  
L’outil de [calcul de capacité 2015 de Skype entreprise Server](https://www.microsoft.com/en-us/download/details.aspx?id=51196) et [skype entreprise Server 2019 de capacités](https://www.microsoft.com/en-us/download/details.aspx?id=57509) renforcent l' [outil de planification de Skype entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=50357) et votre documentation de déploiement ([planifiez votre abonnement Skype entreprise Le déploiement de serveur 2015](../plan-your-deployment/plan-your-deployment.md) et [la planification de votre déploiement de Skype entreprise Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectivement). Utilisez le calculateur après avoir consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.
  
Le calculateur de capacités de Skype entreprise Server vous permet de déterminer les exigences du serveur en fonction du nombre d’utilisateurs et des outils de communication utilisés par votre organisation. Une fois que vous avez déterminé votre profil d’utilisateur et les fonctions que vous voulez activer pour vos utilisateurs, utilisez le calculateur pour déterminer le nombre de serveurs, la quantité de mémoire et la bande passante dont vous aurez besoin. Cette version du calculateur ne fournit pas de recommandations concernant les spécifications des E/S du disque.
  
Vous pouvez tirer pleinement parti du calculateur si vous avez des informations précises et détaillées sur votre profil d’utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs pour lesquels la voix est activée, le nombre moyen d’appels par utilisateur et par heure, la durée des appels et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une différence considérable en matière de configuration du serveur. La précision des recommandations créées par le calculateur dépend de celle des informations que vous fournissez.
  
Une fois que vous avez utilisé les outils de planification et de planification de la capacité, vous devez simuler votre charge proposée et prévue pour vous assurer que Skype entreprise Server sera correctement approvisionné. Pour effectuer des tests de stress en cas de chargement simulé, utilisez l' [outil de stress et de performance de Skype entreprise Server](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documenté dans l' [outil de stress et de performance de Skype entreprise Server](https://technet.microsoft.com/en-us/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Utilisation du calculateur de capacité

Le calculateur est une feuille de calcul Microsoft Excel. Vos cellules d’entrée sont de couleur orange. Les valeurs par défaut sont tapées dans les cellules (par le biais de Skype entreprise Server 2015, 80 000 utilisateurs dans un seul pool avec douze serveurs frontaux, tandis que pour Skype entreprise Server 2019, 106 000 utilisateurs dans un seul pool avec seize serveurs frontaux), vous devez remplacer ces valeurs par correspondent aux besoins de votre organisation.
  
Le modèle d’utilisation contient les sections suivantes. Pour calculer la capacité requise, entrez les données en suivant les instructions, en commençant par le haut de la feuille et en descendant ligne par ligne : 
  
 **Messagerie instantanée et présence**
  
- Sous **Nombre d’utilisateurs**, tapez le nombre d’utilisateurs qui seront connectés simultanément. Ce nombre représente généralement 80 % du nombre total des utilisateurs approvisionnés. Le plus souvent, 100 % de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence. La valeur par défaut est 80 000 pour Skype entreprise Server 2015 et 106 000 utilisateurs pour Skype entreprise Server 2019.
    
- **Nombre moyen de contacts dans la liste de contacts** indique le nombre de contacts utilisé pour valider votre configuration système. Ce nombre est fixe et n’est pas modifiable.
    
  **Voix Entreprise**
  
- Dans **Utilisateurs activés pour Voix Entreprise**, tapez le pourcentage de vos utilisateurs qui sont activés pour Voix Entreprise. La valeur par défaut est 60 %. 
    
- Dans **Nombre moyen d’appels par utilisateur et par heure (pic)**, tapez le nombre d’appels par heure auxquels vous estimez que l’utilisateur moyen participera pendant les heures de pointe. La valeur par défaut est 4. 
    
- Dans **Pourcentage d’appels qui contournent le trafic multimédia**, tapez le pourcentage des appels passés par vos utilisateurs qui contourneront le serveur de médiation. La valeur par défaut est 65 %, mais peut être plus basse si votre organisation est dispersée sur le plan géographique ou si vous avez un pourcentage élevé d’utilisateurs qui travaillent chez eux.
    
- Pour le **pourcentage d’utilisateurs vocaux impliqués dans les appels RTC**, tapez le pourcentage d’appels de votre organisation qui sont des appels de communications unifiées. La valeur par défaut est 60 %.
    
- **Pourcentage d’utilisateurs de la voix participant à des appels UC-UC** indique le pourcentage d’utilisateurs activés pour Voix Entreprise qui ne pourront que passer et recevoir des appels UC-UC. Ce nombre est calculé sur la base de la valeur que vous avez entrée dans le champ **Pourcentage d’utilisateurs de la voix activés pour les appels UC-RTC**. 
    
  **Téléconférence**
  
- Dans **Pourcentage d’utilisateurs dans des conférences simultanées**, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences. La valeur par défaut est 5 %. 
    
- Dans **Pourcentage de conférences avec la messagerie instantanée de groupe uniquement (pas de voix)**, tapez le pourcentage de conférences qui impliqueront uniquement la messagerie instantanée de groupe et n’incluent pas d’audio. La valeur par défaut est 10 %.
    
- Dans **Pourcentage d’utilisateurs utilisant les conférences rendez-vous**, tapez le pourcentage de participants simultanés dans des conférences qui utiliseront les conférences rendez-vous. La valeur par défaut est 15 %.
    
- Dans **Pourcentage de conférences utilisant la voix**, tapez le pourcentage de conférences qui incluront de l’audio. 
    
  - Si 20 % de vos conférences vocales incluront également de la vidéo standard, activez la case à cocher **Vidéo incluse (pas de multi-vue)**.
    
  - Si 20 % de vos conférences incluront également la vidéo multi-vue, activez la case à cocher **Multi-vue incluse**.
    
  - Si 50% de vos conférences vocales incluent également le partage d’application, activez la case à cocher **inclure le partage d’application** .
    
  - Si 20 % de vos conférences vocales incluent des téléchargements de données, tels que des présentations PowerPoint, activez la case à cocher **Conférence web incluse**.
    
  **Mobilité**
  
- Dans **pourcentage d’utilisateurs activés pour la mobilité**, tapez le pourcentage d’utilisateurs qui seront activés pour se connecter à Skype entreprise Server à l’aide d’appareils mobiles. La valeur par défaut est 40 %. 
    
Lorsque vous avez entré toutes les informations nécessaires, le calculateur de capacité évalue votre configuration requise. Les cellules jaunes montrent des valeurs calculées pour le processeur, la mémoire et les exigences de bande passante en fonction des tests exécutés dans Skype entreprise Server-performance Labs. Les nombres sont fournis dans le cadre d’une instruction, et aucune variante unique n’est testée et validée. Les valeurs suivantes sont calculées: 
  
- **Processeur frontal** : pourcentage d’utilisation du processeur si la charge complète est traitée par un serveur frontal dont les spécifications sont identiques à celles du serveur utilisé lors du test (consultez la description à la fin de cet article).
    
- **Réseau (Mbits/s)**  : bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.
    
- **Mémoire (Go)**  : mémoire requise en giga-octets (Go) pour la charge de travail correspondante.
    
Les cellules vertes indiquent les recommandations pour le modèle d’utilisation que vous avez entré. 
  
- **Nombre total de serveurs frontaux**: le nombre de serveurs physiques requis est basé sur des serveurs dédiés exécutant Skype entreprise Server 2015 avec deux processeurs, un cœur hexadécimal, avec 2 260 mégacycles ou Skype entreprise Server 2019 avec Intel Xeon E5-2673 v3, double processeur hex-cœur.
    
    Il est recommandé d’activer l’hyperthreading. Il a été démontré que cette technologie améliore les performances des serveurs prenant en charge le son et la vidéo.
    
- **Serveurs Edge** : nombre de serveurs Edge requis, sur la base de 30 % de tous les utilisateurs communiquant simultanément via les serveurs Edge. Ce pourcentage ne peut pas être modifié dans le calculateur. 
    
- **Magasin pour l’archivage/l’enregistrement des détails des appels/les services de qualité de l’expérience (QoE)**  : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, si celles-ci sont activées dans votre organisation.
    
- **Serveur de base de données principal requis (pools requis)**  : nombre de serveurs de base de données principaux requis pour prendre en charge la charge de travail sélectionnée.
    
Dans la ligne en regard de Nombre total de serveurs frontaux, des informations supplémentaires sont fournies sur la charge sur vos serveurs et le réseau pour les charges de travail combinées.
  
- **Charge processeur moyenne** : utilisation moyenne du processeur par serveur frontal.
    
- **Réseau (en Mbits/s)**  : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.
    
- **Mémoire (en Go)**  : mémoire en giga-octets requise pour chaque serveur frontal.
    
### <a name="adjusting-for-your-processors"></a>Ajustement de vos processeurs

Toutes les valeurs d’utilisation de l’UC dans la feuille de calcul partent du principe que chaque serveur Skype entreprise Server 2015 dispose d’un processeur double-cœur, d’une cœur de 2,26 GHz, d’au moins 32 Go de mémoire et d’au moins 72 Go de disques durs 10 000 Pour chaque serveur Skype entreprise Server 2019, tous les chiffres d’utilisation de l’UC dans la feuille de calcul partent du principe que chaque serveur possède un processeur double, un cœur à cœur fixe avec Intel Xeon E5-2673 v3, au moins 64 Go de mémoire, et 8 72 lecteurs de disque dur 10 000 rythme.
  
Si vos serveurs ont d’autres processeurs, vous pouvez modifier les chiffres pour les adapter à votre matériel.
  
