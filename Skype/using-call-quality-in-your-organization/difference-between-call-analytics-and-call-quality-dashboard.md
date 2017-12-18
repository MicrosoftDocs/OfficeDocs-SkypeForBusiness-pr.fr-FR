---
title: "Quelle est la différence entre appeler Analytique et tableau de bord qualité d'appel ?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
description: "Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business."
---

# Quelle est la différence entre appeler Analytique et tableau de bord qualité d'appel ?

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Skype Entreprise vous propose deux méthodes pour surveiller et résoudre les problèmes de qualité des appels : appel Analytique et tableau de bord qualité d'appel. Cet article décrit les deux et vous signale quand utiliser chacun d'eux.
  
> [!NOTE]
> Appel Analytique est en cours d'aperçu. Texte et les images ci-dessus peut ne pas correspondent votre expérience. 
  
## Qu'est appeler Analytique, et quand dois-je l'utiliser ?

Appel Analytique affiche des informations détaillées sur les appareils, réseaux et connectivité lié aux appels spécifiques et réunions pour chaque utilisateur dans un compte Skype Entreprise. Si vous êtes un administrateur Skype Entreprise, vous pouvez utiliser Analytique appeler pour résoudre les problèmes de connexion et de qualité Skype Entreprise appel.
  
Si vous souhaitez que non-Admin, tels que des agents du support technique à partir d'un fournisseur externe, pour utiliser appeler Analytique, vous pouvez attribuer des autorisations afin qu'ils peuvent utiliser appeler Analytique, mais ils ne peuvent pas accéder au reste Skype Entreprise centre d'administration :
  
- **Support technique agents avec des autorisations de niveau 1**: Agents voir un jeu de données et d'informations d'identification personnelle (personnelles) dans appeler Analytique limité. Ils peuvent dépanner appels, mais ils transmet problèmes liés aux réunions à un agent de niveau 2.
    
- **Support technique agents avec des autorisations de niveau 2**: Agents voir toutes les données disponibles dans appeler Analytique et résoudre les problèmes d'appels et réunions. Ils disposent d'un accès complet à appeler les journaux et les informations relatives aux clients.
    
Pour plus d'informations sur la configuration d'appel Analytique, voir [Configurer Skype pour les entreprises appeler Analytique](set-up-skype-for-business-call-analytics.md). Pour plus d'informations sur comment agents du support technique peuvent fonctionner avec appel Analytique, voir [Qualité des appels utilisation appeler Analytique pour résoudre un problème Skype pour les entreprises](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md).
  
## Quel est le tableau de bord qualité d'appel, et quand dois-je l'utiliser ?

Appel Analytique vous donne des informations détaillées et spécifiques sur la qualité des appels rencontrée par les utilisateurs. Pourquoi utilisateur Tony Smith disposer d'un appel mauvaise cet après-midi ? À l'aide d'appel Analytique, un agent de support technique formé ou Skype Entreprise administrateur pouvez analyser le périphérique, réseau, connectivité et autres facteurs liés à l'appel de Tony.
  
Où autorité de certification est conçue pour aider les administrateurs et du support technique agents résoudre les problèmes de qualité appel des appels spécifiques, le tableau de bord de la qualité d'appel (CQD) est conçu pour aider les administrateurs Skype Entreprise et ingénieurs réseau optimisent un réseau. CQD déplace le focus des utilisateurs spécifiques et à la place ressemble à regrouper les informations pour une organisation entière Skype Entreprise.
  
La qualité des appels un problème de Tony est peut-être en raison d'un problème de réseau qui affecte également grand nombre d'autres utilisateurs. Expérience d'appels individuels de Tony n'est pas visible dans CQD, mais la qualité générale des appels effectuées à l'aide de Skype Entreprise est capturée. Avec la CQD global motifs peuvent apparaître, permettant aux ingénieurs réseau à évaluer informé de la qualité des appels. CQD fournit des rapports de métriques de qualité d'appel qui donnent des idées en appellent global qualité, flux serveur-client et client client et la qualité de voix [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Pour plus d'informations, voir [Fonctionnalités du tableau de bord de qualité des appels de Skype Entreprise Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_FeaturesOfTheCQD).
  
Appel Analytique et CQD s'exécuter en parallèle et peuvent être utilisé indépendamment ou ensemble. Par exemple, qu'un agent de niveau 1 détermine la façon dont ils ont besoin d'une aide supplémentaire pour résoudre un problème d'appel. L'agent de niveau 1 transmet l'appel à un agent de niveau 2, qui accèdent à plus d'informations dans appeler Analytique que l'agent de niveau 1. L'agent de niveau 2 alerte à son tour un technicien réseau pour un problème. Le technicien du réseau peut vérifier CQD pour voir si un problème global relative au site pourrait être la cause contribue des problèmes d'appel.
  
Pour plus d'informations sur CQD, voir [Activation et à l'aide de tableau de bord qualité d'appel pour Microsoft Teams et Skype entreprise Online](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md) et les[Dimensions et mesures disponibles dans appeler la qualité du tableau de bord pour Microsoft Teams et Skype entreprise Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

