---
title: Calculateur de planification de la capacité pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Résumé : Comment faire pour utiliser l’outil de calcul de capacité.'
ms.openlocfilehash: 5d94dab15b104703efc76b227e6e9dd1286f9955
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-capacity-planning-calculator"></a>Calculateur de planification de la capacité pour Skype Entreprise Server 2015
 
**Résumé :** comment utiliser l’outil calculateur de capacité.
  
[Skype pour la calculatrice de capacité 2015 Business Server](https://www.microsoft.com/en-us/download/details.aspx?id=51196) augmente le [Skype pour outil de planification commerciale 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357) et la documentation à [planifier votre Skype pour le déploiement de Business Server 2015](https://technet.microsoft.com/en-us/library/dn951427). Utilisez le calculateur après avoir consulté le guide et créé une topologie recommandée à l’aide de l’outil de planification.
  
Le Skype pour la calculatrice de capacité 2015 Business Server vous permet de vous déterminez les besoins de serveur en fonction du nombre d’utilisateurs et les outils de communication que votre organisation utilise. Une fois que vous avez déterminé votre profil d’utilisateur et les fonctions que vous voulez activer pour vos utilisateurs, utilisez le calculateur pour déterminer le nombre de serveurs, la quantité de mémoire et la bande passante dont vous aurez besoin. Cette version du calculateur ne fournit pas de recommandations concernant les spécifications des E/S du disque.
  
Vous pouvez tirer pleinement parti du calculateur si vous avez des informations précises et détaillées sur votre profil d’utilisateur spécifique. Par exemple, le pourcentage d’utilisateurs pour lesquels la voix est activée, le nombre moyen d’appels par utilisateur et par heure, la durée des appels et le pourcentage d’utilisateurs simultanés dans les conférences peuvent faire une différence considérable en matière de configuration du serveur. La précision des recommandations créées par le calculateur dépend de celle des informations que vous fournissez.
  
Une fois que vous avez utilisé l’outil de planification et de la calculatrice de planification de capacité, vous devez simuler la charge proposée et planifiée pour vous assurer que Skype pour Business Server 2015 sera déployé correctement. Pour effectuer les tests sous une charge simulée de stress, utiliser le [Skype pour Business Server 2015 Stress et l’outil performances](https://www.microsoft.com/en-us/download/details.aspx?id=50367) [Skype pour Business Server 2015 Stress et l’outil performances](https://technet.microsoft.com/en-us/library/mt631400.aspx)de documentation.
  
## <a name="using-the-capacity-calculator"></a>Utilisation du calculateur de capacité

Le calculateur est une feuille de calcul Microsoft Excel. Vos cellules d’entrée sont de couleur orange. Valeurs par défaut sont entrées dans les cellules (par exemple, 80 000 utilisateurs dans un seul pool avec douze serveurs frontaux), mais vous devez modifier ces valeurs en fonction des besoins de votre organisation. 
  
Le modèle d’utilisation contient les sections suivantes. Pour calculer la capacité requise, entrez les données en suivant les instructions, en commençant par le haut de la feuille et en descendant ligne par ligne : 
  
 **Messagerie instantanée et présence**
  
- Sous **Nombre d’utilisateurs**, tapez le nombre d’utilisateurs qui seront connectés simultanément. Ce nombre représente généralement 80 % du nombre total des utilisateurs approvisionnés. Le plus souvent, 100 % de vos utilisateurs simultanés seront activés pour la messagerie instantanée et la présence. La valeur par défaut est 80 000.
    
- **Nombre moyen de contacts dans la liste de contacts** indique le nombre de contacts utilisé pour valider votre configuration système. Ce nombre est fixe et n’est pas modifiable.
    
 **Voix Entreprise**
  
- Dans **Utilisateurs activés pour Voix Entreprise**, tapez le pourcentage de vos utilisateurs qui sont activés pour Voix Entreprise. La valeur par défaut est 60 %. 
    
- Dans **Nombre moyen d’appels par utilisateur et par heure (pic)**, tapez le nombre d’appels par heure auxquels vous estimez que l’utilisateur moyen participera pendant les heures de pointe. La valeur par défaut est 4. 
    
- Dans **Pourcentage d’appels qui contournent le trafic multimédia**, tapez le pourcentage des appels passés par vos utilisateurs qui contourneront le serveur de médiation. La valeur par défaut est 65 %, mais peut être plus basse si votre organisation est dispersée sur le plan géographique ou si vous avez un pourcentage élevé d’utilisateurs qui travaillent chez eux.
    
- **Pourcentage de voix les utilisateurs impliqués dans les appels de communications unifiées-PSTN**, tapez le pourcentage d’appels de votre organisation qui sont les appels RTPC-CU. La valeur par défaut est 60 %.
    
- **Pourcentage d’utilisateurs de la voix participant à des appels UC-UC** indique le pourcentage d’utilisateurs activés pour Voix Entreprise qui ne pourront que passer et recevoir des appels UC-UC. Ce nombre est calculé sur la base de la valeur que vous avez entrée dans le champ **Pourcentage d’utilisateurs de la voix activés pour les appels UC-RTC**. 
    
 **Téléconférence**
  
- Dans **Pourcentage d’utilisateurs dans des conférences simultanées**, tapez le pourcentage d’utilisateurs qui participeront simultanément à des conférences. La valeur par défaut est 5 %. 
    
- Dans **Pourcentage de conférences avec la messagerie instantanée de groupe uniquement (pas de voix)**, tapez le pourcentage de conférences qui impliqueront uniquement la messagerie instantanée de groupe et n’incluent pas d’audio. La valeur par défaut est 10 %.
    
- Dans **Pourcentage d’utilisateurs utilisant les conférences rendez-vous**, tapez le pourcentage de participants simultanés dans des conférences qui utiliseront les conférences rendez-vous. La valeur par défaut est 15 %.
    
- Dans **Pourcentage de conférences utilisant la voix**, tapez le pourcentage de conférences qui incluront de l’audio. 
    
  - Si 20 % de vos conférences vocales incluront également de la vidéo standard, activez la case à cocher **Vidéo incluse (pas de multi-vue)**.
    
  - Si 20 % de vos conférences incluront également la vidéo multi-vue, activez la case à cocher **Multi-vue incluse**.
    
  - 50 % de vos conférences vocales inclura également le partage d’application, activez la case à cocher **, y compris le partage d’application** .
    
  - Si 20 % de vos conférences vocales incluent des téléchargements de données, tels que des présentations PowerPoint, activez la case à cocher **Conférence web incluse**.
    
 **Mobilité**
  
- **Pourcentage des utilisateurs activés pour la mobilité**, tapez le pourcentage de vos utilisateurs autorisés à se connecter sur Skype pour Business Server à l’aide de périphériques mobiles. La valeur par défaut est 40 %. 
    
Lorsque vous avez entré toutes les informations nécessaires, la calculatrice de capacité évalue vos besoins. Les cellules jaunes indiquent les valeurs calculées pour le processeur, la mémoire et la bande passante en fonction des tests effectués dans Skype pour les laboratoires de performances Business Server. Les numéros sont fournies à titre indicatif, pas chaque variation unique est testée et validée. Les valeurs suivantes sont calculées : 
  
- **Processeur frontal** : pourcentage d’utilisation du processeur si la charge complète est traitée par un serveur frontal dont les spécifications sont identiques à celles du serveur utilisé lors du test (consultez la description à la fin de cet article).
    
- **Réseau (Mbits/s)** : bande passante requise en mégabits par seconde (Mbits/s) pour la charge de travail correspondante.
    
- **Mémoire (Go)** : mémoire requise en giga-octets (Go) pour la charge de travail correspondante.
    
Les cellules vertes indiquent les recommandations pour le modèle d’utilisation que vous avez entré. 
  
- **Nombre total de serveurs frontaux** : le nombre de serveurs physiques requis est basé sur les serveurs dédiés exécutant Skype Entreprise Server 2015 avec biprocesseur, hexa-cœur et 2 260 mégacycles.
    
    Il est recommandé d’activer l’hyperthreading. Il a été démontré que cette technologie améliore les performances des serveurs prenant en charge le son et la vidéo.
    
- **Serveurs Edge** : nombre de serveurs Edge requis, sur la base de 30 % de tous les utilisateurs communiquant simultanément via les serveurs Edge. Ce pourcentage ne peut pas être modifié dans le calculateur. 
    
- **Magasin pour l’archivage/l’enregistrement des détails des appels/les services de qualité de l’expérience (QoE)** : nombre de magasins requis pour les fonctionnalités d’archivage ou de surveillance, si celles-ci sont activées dans votre organisation.
    
- **Serveur de base de données principal requis (pools requis)** : nombre de serveurs de base de données principaux requis pour prendre en charge la charge de travail sélectionnée.
    
Dans la ligne en regard de Nombre total de serveurs frontaux, des informations supplémentaires sont fournies sur la charge sur vos serveurs et le réseau pour les charges de travail combinées.
  
- **Charge processeur moyenne** : utilisation moyenne du processeur par serveur frontal.
    
- **Réseau (en Mbits/s)** : allocation de bande passante requise pour prendre en charge le modèle d’utilisation que vous avez entré.
    
- **Mémoire (en Go)** : mémoire en giga-octets requise pour chaque serveur frontal.
    
### <a name="adjusting-for-your-processors"></a>Ajustement de vos processeurs

Tous les chiffres relatifs à l’utilisation du processeur dans la feuille de calcul partent du principe que chaque serveur est équipé d’un biprocesseur, hexa-cœur avec 2,26 GHz, 32 Go de mémoire au minimum, et 8 (ou plus) disques durs d’une vitesse de 10 000 RPM avec au moins 72 Go d’espace disponible. 
  
Si vos serveurs ont d’autres processeurs, vous pouvez modifier les chiffres pour les adapter à votre matériel.
  

