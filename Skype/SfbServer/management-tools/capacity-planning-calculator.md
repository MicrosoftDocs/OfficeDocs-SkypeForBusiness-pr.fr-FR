---
title: Calculateur de planification de la capacité Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Résumé : Utilisation de l’outil calculatrice de capacité.'
ms.openlocfilehash: 37df48310e14b31b42bbcaa9d8f5ef89ef7341e0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409957"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculateur de planification de la capacité Skype Entreprise Server
 
**Résumé :** Utilisation de l’outil Calculatrice de capacité.

> [!NOTE]
> Cet article fait référence Skype Entreprise Server téléchargements 2015, mais il s’applique à :
> - Skype Entreprise Server 2019.
> - Skype Entreprise Server 2015.
  
La [calculatrice de capacité Skype Entreprise Server 2015](https://www.microsoft.com/download/details.aspx?id=51196) et la calculatrice de capacité [Skype Entreprise Server 2019](https://www.microsoft.com/download/details.aspx?id=57509) complètent l’outil de planification [Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=50357) et votre documentation de déploiement (planifier [votre Skype Entreprise Server  Déploiement 2015 et](../plan-your-deployment/plan-your-deployment.md) [planifier votre déploiement Skype Entreprise Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md), respectivement). Utilisez la calculatrice après avoir consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.
  
Le calculateur Skype Entreprise Server capacité vous permet de déterminer les besoins du serveur en fonction du nombre d’utilisateurs et des outils de communication utilisés par votre organisation. Une fois que vous avez déterminé votre profil utilisateur et les fonctions que vous souhaitez activer pour vos utilisateurs, utilisez la calculatrice pour déterminer le nombre de serveurs, de mémoire et de bande passante dont vous aurez besoin. Cette version de la calculatrice ne fournit pas de conseils pour les besoins en matière d’entrée//de-fin de disque.
  
Vous pouvez tirer le meilleur parti de la calculatrice si vous avez des informations précises et détaillées sur votre profil utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs à reconnaissance vocale, le nombre moyen d’appels par utilisateur et par heure, la durée des appels et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une différence considérable dans les besoins du serveur. La précision des recommandations créées par la calculatrice dépend de la précision des informations que vous fournissez.
  
Une fois que vous avez utilisé l’outil de planification et la calculatrice de planification de la capacité, vous devez simuler la charge proposée et planifiée pour vous assurer que Skype Entreprise Server sera correctement mise en service. Pour effectuer des tests de contrainte sous une charge simulée, utilisez l’outil [Skype Entreprise Server Stress and Performance](https://www.microsoft.com/download/details.aspx?id=50367) de l’Skype Entreprise Server [l’outil Stress and Performance](./stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="using-the-capacity-calculator"></a>Utilisation de la calculatrice de capacité

La calculatrice est une feuille Microsoft Excel feuille de calcul. Vos cellules d’entrée sont de couleur orange. Les valeurs par défaut sont entrées dans les cellules (pour Skype Entreprise Server 2015, 80 000 utilisateurs dans un pool avec douze serveurs frontaux, tandis que pour Skype Entreprise Server 2019, 106 000 utilisateurs dans un pool avec 16 serveurs frontaux), mais vous devez modifier ces valeurs pour répondre aux besoins de votre organisation.
  
Le modèle d’utilisation contient les sections suivantes. Pour calculer vos besoins en capacité, entrez les données comme décrit en commençant en haut de la feuille et en travaillant ligne par ligne vers le bas : 
  
 **Messagerie instantanée et présence**
  
- Sous **Nombre d’utilisateurs**, tapez le nombre d’utilisateurs qui seront signés à la fois. Ce nombre est généralement de 80 % du nombre total d’utilisateurs provisionnés. Dans la plupart des cas, 100 % de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence. La valeur par défaut est 80 000 pour Skype Entreprise Server 2015 et 106 000 utilisateurs pour Skype Entreprise Server 2019.
    
- **Le nombre moyen de contacts dans la liste des** contacts indique le nombre de contacts que nous utilisons pour valider votre système requis. Ce nombre est fixe et ne doit pas être changé.
    
  **Voix Entreprise**
  
- Dans **Utilisateurs activés pour Voix Entreprise**, tapez le pourcentage de vos utilisateurs activés pour Voix Entreprise. La valeur par défaut est 60 %. 
    
- En **nombre moyen d’appels par utilisateur et par heure (pointe),** tapez le nombre d’appels par heure que l’utilisateur moyen doit participer aux heures de pointe. La valeur par défaut est 4. 
    
- Dans **Pourcentage d’appels qui utilisent le contournement de** média, tapez le pourcentage d’appels passé par vos utilisateurs qui contournera le serveur de médiation. La valeur par défaut est de 65 %, mais elle peut être inférieure si vous êtes dispersé géographiquement ou si vous avez un grand pourcentage d’utilisateurs qui travaillent à domicile.
    
- Dans **Pourcentage d’utilisateurs** vocaux impliqués dans les appels UC-PSTN, tapez le pourcentage d’appels de votre organisation qui sont des appels téléphoniques UC-PSTN. La valeur par défaut est 60 %.
    
- Le pourcentage d’utilisateurs vocaux impliqués dans les appels **UC-UC** indique le pourcentage d’utilisateurs activés pour Voix Entreprise qui seront activés uniquement pour les appels UC-UC. Ce nombre est calculé en fonction du pourcentage d’utilisateurs vocaux activés pour les appels **UC-PSTN**. 
    
  **Conférence**
  
- Dans **Pourcentage d’utilisateurs participant à des conférences simultanées**, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences. La valeur par défaut est 5 %. 
    
- Dans **Pourcentage de conférences avec** messagerie instantanée de groupe uniquement (sans voix), tapez le pourcentage de conférences qui impliqueront uniquement la messagerie instantanée et n’incluent pas l’audio. La valeur par défaut est 10 %
    
- Dans **Pourcentage d’utilisateurs** utilisant la conférence téléphonique, tapez le pourcentage de participants aux conférences qui utiliseront les conférences téléphoniques à la fois. La valeur par défaut est 15 %.
    
- Dans **Pourcentage de conférences utilisant la voix**, tapez le pourcentage de conférences qui incluront l’audio. 
    
  - Si 20 % de vos conférences vocales incluent également une vidéo régulière, cochez la case Inclure la vidéo **(sans affichage multiple** ).
    
  - Si 20 % de vos conférences incluent également une vidéo multi-affichage, cochez la case Inclure **un affichage** multiple.
    
  - Si 50 % de vos conférences vocales incluent également le partage d’application, cochez la case Inclure **le partage d’application** .
    
  - Si 20 % de vos conférences vocales incluent des téléchargements de données, tels que PowerPoint présentations, cochez la case Inclure la conférence **web**.
    
  **Mobilité**
  
- Dans **Pourcentage d’utilisateurs** activés pour la mobilité, tapez le pourcentage de vos utilisateurs qui seront activés pour se connecter à Skype Entreprise Server’aide d’appareils mobiles. La valeur par défaut est 40 %. 
    
Une fois que vous avez entré toutes les informations nécessaires, le calculateur de capacité évalue vos besoins. Les cellules jaunes indiquent les valeurs calculées pour les besoins en processeur, en mémoire et en bande passante en fonction des tests effectués dans Skype Entreprise Server’ateliers de performances. Les nombres sont fournis à titre indicatif, et toutes les variantes ne sont pas testées et validées. Les valeurs suivantes sont calculées : 
  
- Processeur frontal : pourcentage d’utilisation du processeur si la charge entière a été gérée par un serveur frontal des mêmes spécifications que le serveur utilisé lors des tests (voir la description à la fin de cet article).
    
- **Réseau en Mbits/s** : besoins en bande passante en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.
    
- **Mémoire en Go** : mémoire requise en gigaoctets (Go) pour la charge de travail correspondante.
    
Les cellules vertes indiquent des recommandations pour le modèle d’utilisation que vous avez entré. 
  
- Nombre total de serveurs frontaux : le nombre de serveurs physiques requis est basé sur des serveurs dédiés exécutant Skype Entreprise Server 2015 avec deux processeurs, hexa-cœurs, avec 2 260 mégacycles, ou Skype Entreprise Server 2019 avec Intel Xeon E5-2673 v3, double processeur, hex-core.
    
    Notez que l’activation de l’hyperthreading est recommandée et a été démontrée pour améliorer les performances pour les serveurs qui utilisent l’audio/vidéo.
    
- **Serveurs Edge :** nombre de serveurs Edge requis, sur la base de 30 % de tous les utilisateurs simultanés communiquant via les serveurs Edge. Ce pourcentage ne peut pas être modifié dans la calculatrice. 
    
- **Magasin de** services d’archivage/d’enregistrement des détails des appels/qualité de l’expérience : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, s’ils sont activés dans votre organisation.
    
- **Serveur de base de données principal requis (pools requis)** : nombre de serveurs de base de données principal requis pour prendre en charge la charge de travail sélectionnée.
    
En outre, dans la ligne en face du nombre total de serveurs frontaux, des informations supplémentaires sont fournies sur la charge sur vos serveurs et votre réseau pour toutes les charges de travail planifiées combinées.
  
- **Charge processeur moyenne :** utilisation moyenne du processeur par serveur frontal.
    
- **Réseau en Mbits/s** : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.
    
- **Mémoire en Go** : mémoire, en gigaoctets, requise pour chaque serveur frontal.
    
### <a name="adjusting-for-your-processors"></a>Ajustement pour vos processeurs

Toutes les figures d’utilisation de l’UC dans la feuille de calcul supposent que chaque serveur Skype Entreprise Server 2015 dispose d’un double processeur, d’un cœur hex core avec 2,26 GHz, d’au moins 32 Go de mémoire et d’au moins 8 disques durs de 10 000 MPM avec au moins 72 Go d’espace disque libre. Pour chaque serveur Skype Entreprise Server 2019, toutes les figures d’utilisation de l’UC dans la feuille de calcul supposent que chaque serveur dispose d’un double processeur, d’un système hexa-cœur avec Intel Xeon E5-2673 v3, d’au moins 64 Go de mémoire et d’au moins 8 disques durs 10 000 RPM avec au moins 72 Go d’espace disque libre.
  
Si vos serveurs ont des processeurs différents, vous pouvez ajuster les chiffres pour qu’ils correspondent à votre matériel.
