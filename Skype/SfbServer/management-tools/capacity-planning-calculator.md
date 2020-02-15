---
title: Calculatrice de planification de la capacité de Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Résumé : comment utiliser l’outil calculateur de capacité.'
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031078"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculatrice de planification de la capacité de Skype entreprise Server
 
**Résumé :** Comment utiliser l’outil calculateur de capacité.

> [!NOTE]
> Cet article fait référence aux téléchargements de Skype entreprise Server 2015, mais s’applique à :
> - Skype entreprise Server 2019.
> - Skype entreprise Server 2015.
  
Le calculateur de [capacité Skype entreprise server 2015](https://www.microsoft.com/download/details.aspx?id=51196) et [skype entreprise Server 2019](https://www.microsoft.com/download/details.aspx?id=57509) augmentent l' [outil de planification de Skype entreprise](https://www.microsoft.com/download/details.aspx?id=50357) et votre documentation de déploiement ([planifiez votre déploiement](../plan-your-deployment/plan-your-deployment.md) de Skype entreprise Server 2015 et [planifiez votre déploiement de Skype entreprise Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) , respectivement). Utilisez la calculatrice une fois que vous avez consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.
  
Le calculateur de capacité Skype entreprise Server vous aide à déterminer la configuration requise pour le serveur en fonction du nombre d’utilisateurs et des outils de communication utilisés par votre organisation. Une fois que vous avez déterminé votre profil utilisateur et les fonctions que vous souhaitez activer pour vos utilisateurs, utilisez la calculatrice pour déterminer le nombre de serveurs, la mémoire et la bande passante dont vous aurez besoin. Cette version de la calculatrice ne fournit pas d’instructions pour les besoins en e/s disque.
  
Vous pouvez tirer le meilleur parti de la calculatrice si vous disposez d’informations précises et détaillées sur votre profil utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs à extension vocale, le nombre moyen d’appels par utilisateur et par heure, la durée de l’appel et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une très grande différence en termes de serveur. La précision des recommandations créées par la calculatrice dépend de la précision des informations que vous fournissez.
  
Une fois que vous avez utilisé l’outil de planification et le calculateur de planification de la capacité, vous devez simuler votre charge proposée et planifiée pour vous assurer que Skype entreprise Server sera configuré de manière appropriée. Pour effectuer des tests de contrainte sous une charge simulée, utilisez l' [outil de stress et de performances de Skype entreprise Server](https://www.microsoft.com/download/details.aspx?id=50367) documenté dans l' [outil de stress et de performances de Skype entreprise Server](https://technet.microsoft.com/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Utilisation de la calculatrice de capacité

La calculatrice est une feuille de calcul Microsoft Excel. Vos cellules d’entrée sont colorées en orange. Les valeurs par défaut sont entrées dans les cellules (pour Skype entreprise Server 2015, 80 000 les utilisateurs dans un pool avec douze serveurs frontaux, tandis que pour Skype entreprise Server 2019, 106 000 utilisateurs dans un pool avec seize serveurs frontaux), mais vous devez modifier ces valeurs pour répondre aux besoins de votre organisation.
  
Le modèle d’utilisation contient les sections suivantes. Pour calculer vos besoins en termes de capacité, entrez les données comme décrit en haut de la feuille et ligne de bas ligne par ligne : 
  
 **Messagerie instantanée et présence**
  
- Sous **nombre d’utilisateurs**, tapez le nombre d’utilisateurs qui seront connectés en même temps. Ce nombre est généralement de 80% du nombre total d’utilisateurs configurés. Dans la plupart des cas, 100% de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence. La valeur par défaut est 80 000 pour Skype entreprise Server 2015 et 106 000 utilisateurs pour Skype entreprise Server 2019.
    
- **Nombre moyen de contacts dans la liste** de contacts indique le nombre de contacts que nous utilisons pour valider la configuration système requise. Ce nombre est fixe et ne doit pas être modifié.
    
  **Voix Entreprise**
  
- Dans **utilisateurs activés pour voix entreprise**, tapez le pourcentage de vos utilisateurs activés pour voix entreprise. La valeur par défaut est 60%. 
    
- En **nombre moyen d’appels par utilisateur et par heure (PIC)**, tapez le nombre d’appels par heure pendant lesquels vous prévoyez que l’utilisateur moyen participe pendant les périodes de charge maximale. La valeur par défaut est 4. 
    
- Dans **pourcentage des appels qui utilisent**la déviation du trafic multimédia, tapez le pourcentage d’appels passés par vos utilisateurs pour contourner le serveur de médiation. La valeur par défaut est 65%, mais elle peut être inférieure si vous êtes dispersé géographiquement ou si vous avez un pourcentage important d’utilisateurs qui travaillent à partir de la maison.
    
- Dans **pourcentage des utilisateurs vocaux impliqués dans les appels UC-PSTN**, tapez le pourcentage des appels de votre organisation qui sont des appels de téléphone de communications unifiées. La valeur par défaut est 60%.
    
- **Pourcentage d’utilisateurs vocaux impliqués dans les appels UC-UC** indique le pourcentage d’utilisateurs activés pour voix entreprise qui seront activés uniquement pour les appels UC-UC. Ce nombre est calculé en fonction de ce que vous entrez pour le **pourcentage d’utilisateurs vocaux activé pour les appels UC-PSTN**. 
    
  **Vidéoconférence**
  
- Dans **pourcentage d’utilisateurs dans des conférences simultanées**, tapez le pourcentage d’utilisateurs qui participeront à des conférences en même temps. La valeur par défaut est 5%. 
    
- Dans **pourcentage de conférences avec la messagerie instantanée de groupe uniquement (pas de voix)**, tapez le pourcentage de conférences qui impliqueront uniquement la messagerie instantanée et n’incluez pas l’audio. La valeur par défaut est 10%.
    
- Dans **pourcentage des utilisateurs qui utilisent la Conférence**rendez-vous, tapez le pourcentage des participants à des conférences qui utiliseront la Conférence rendez-vous en une seule fois. La valeur par défaut est 15%.
    
- Dans **pourcentage de conférences à l’aide**de la voix, tapez le pourcentage de conférences qui comprendront de l’audio. 
    
  - Si 20% de vos conférences vocales incluent également une vidéo normale, activez la case à cocher **y compris la vidéo (pas de multi-vue)** .
    
  - Si 20% de vos conférences incluent également la vidéo multi-vue, activez la case à cocher **incluant plusieurs vues** .
    
  - Si 50% de vos conférences vocales incluent également le partage d’application, activez la case à cocher **inclure le partage d’applications** .
    
  - Si 20% de vos conférences vocales incluent des téléchargements de données, tels que des présentations PowerPoint, activez la case à cocher **inclure la conférence Web** .
    
  **Mobilité**
  
- Dans **pourcentage d’utilisateurs activés pour la mobilité**, tapez le pourcentage de vos utilisateurs qui seront activés pour se connecter à Skype entreprise Server à l’aide d’appareils mobiles. La valeur par défaut est 40%. 
    
Une fois que vous avez entré toutes les informations nécessaires, la calculatrice de capacité estime votre configuration requise. Les cellules jaunes affichent les valeurs calculées pour l’UC, la mémoire et les besoins en bande passante en fonction des tests effectués dans Skype entreprise Server performance Labs. Les numéros sont fournis en tant qu’indications, et toutes les variantes ne sont pas testées et validées. Les valeurs suivantes sont calculées : 
  
- **Processeur frontal**: pourcentage d’utilisation de l’UC si la totalité de la charge a été gérée par un serveur frontal des mêmes spécifications que le serveur utilisé lors des tests (voir la description à la fin de cet article).
    
- **Réseau en Mbits/s**: bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.
    
- **Mémoire en Go**: mémoire requise en gigaoctets (Go) pour la charge de travail correspondante.
    
Les cellules vertes affichent des recommandations pour le modèle d’utilisation que vous avez entré. 
  
- Nombre **total de serveurs frontaux**: le nombre de serveurs physiques requis est basé sur des serveurs dédiés exécutant Skype entreprise Server 2015 avec deux processeurs, hex-Core, avec 2 260 mégacycles ou Skype entreprise Server 2019 avec Intel Xeon E5-2673 v3, biprocesseur, hex-Core.
    
    Notez que l’activation de l’hyperthreading est recommandée et a été prouvée pour améliorer les performances des serveurs qui prennent en charge l’audio/vidéo.
    
- **Serveurs Edge**: nombre de serveurs Edge requis, basé sur 30% de tous les utilisateurs simultanés communiquant via les serveurs Edge. Ce pourcentage ne peut pas être modifié dans la calculatrice. 
    
- **Magasin d’archivage/d’appel des détails d’enregistrement/de qualité de l’expérience**: nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, s’ils sont activés dans votre organisation.
    
- **Serveur de base de données principal requis (pools requis)**: nombre de serveurs de base de données principaux requis pour prendre en charge la charge de travail sélectionnée.
    
En outre, dans la ligne en regard de serveurs frontaux totaux, des informations supplémentaires sont fournies sur la charge de vos serveurs et de votre réseau pour toutes les charges de travail associées.
  
- **Charge moyenne**de l’UC : utilisation moyenne du processeur par serveur frontal.
    
- **Réseau en Mbits/s**: allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.
    
- **Mémoire en Go**: mémoire, en gigaoctets, requise pour chaque serveur frontal.
    
### <a name="adjusting-for-your-processors"></a>Ajustement pour vos processeurs

Toutes les valeurs d’utilisation du processeur de la feuille de calcul supposent que chaque serveur Skype entreprise Server 2015 dispose d’un double processeur, d’un cœur avec 2,26 GHz, d’au moins 32 Go de mémoire et de 8 disques durs 10 000-tr/min avec au moins 72 Go d’espace disque disponible. Pour chaque serveur Skype entreprise Server 2019, tous les chiffres d’utilisation du processeur de la feuille de calcul partent du principe que chaque serveur est doté d’un double processeur, d’une base hexadécimale avec Intel Xeon E5-2673 v3, d’au moins 64 Go de mémoire et de 8 disques durs 10 000-RPM avec au moins 72 Go de disque libre Pace.
  
Si vos serveurs ont des processeurs différents, vous pouvez ajuster les chiffres pour qu’ils correspondent à votre matériel.
  
