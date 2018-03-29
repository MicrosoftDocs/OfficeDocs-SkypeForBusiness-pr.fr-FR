---
title: Planifier Skype Entreprise dans des environnements VDI
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Cette rubrique décrit les considérations de planification pour l’aide Skype pour entreprise lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: facf154940b7a82ddc41ac07b87a8af1a5313f5e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planifier Skype Entreprise dans des environnements VDI
 
Cette rubrique décrit les considérations de planification pour l’aide Skype pour entreprise lors de la connexion à un bureau virtuel distant. 
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux. Dans ces entreprises, les utilisateurs effectuent leur travail sur un bureau virtuel avec tous leurs fichiers et applications de bureau à l’aide des services Bureau à distance ou d’une connexion distante similaire. À l’aide de Skype pour entreprise avec audio et vidéo sur une connexion complète que nécessitent des charges lourdes de données audio et vidéo de traitement sur le client hébergés sur un bureau virtuel. Un plug-in logiciel VDI supplémentaire n’est disponible qui décharge le traitement à l’ordinateur local de l’utilisateur final et réduit la charge sur le bureau virtuel.
  
Il existe trois solutions disponibles pour le composant plug-in de VDI, offert par Microsoft, Citrix ou VMWare. Pour les nouveaux déploiements, Microsoft recommande d’utiliser la solution en temps réel Optimization Pack Citrix HDX ou le Pack de la virtualisation VMWare Horizon. Le plug-in de VDI Lync d’origine est toujours pris en charge pour le reste de son cycle de vie.
  
- Le **Plug-in à Lync VDI** a été développé pour Lync 2013 et est compatible avec Skype ou Lync 2013 pour client d’entreprise 2015 s’exécutant sur un ordinateur de bureau virtuel. Il s’agit d’une application autonome qui s’installe sur l’ordinateur local et permet d’utiliser des périphériques audio et vidéo locaux avec un client sur un bureau virtuel. Le plug-in ne nécessite pas un Skype pour client d’entreprise doit être installé sur l’ordinateur local ou d’un client léger, qui doit exécuter les systèmes d’exploitation Windows Server 2008, Windows 7 et Windows 8. (Incluent les périphériques de client léger à l’aide de ces systèmes d’exploitation et prise en charge par Microsoft : Z90D7 de Wyse Dell, Dell Wyse R90L7, Dell Wyse X90m7, t610 de HP et HP t5740e.) Ce plug-in est toujours pris en charge, mais aucuns les mises à jour ne sont planifiées. Pour les environnements virtuels Citrix, le pack d’optimisation Citrix RealTime est recommandé.
    
- Le **Pack d’optimisation Citrix en temps réel** repose sur le plug-in de VDI Lync et fonctionne avec Lync 2013 ou Skype pour les clients d’entreprise 2016 sur un bureau virtuel. Il a été développé conjointement par Citrix et Microsoft pour offrir des améliorations du plug-in VDI d’origine. Il peut s’installer sur des clients avec des systèmes d’exploitation Windows et non Windows (y compris Windows 10, Mac et Linux). Il se compose de deux composants : le connecteur en temps réel (ce qui est installé sur le poste de travail virtuel) et le moteur de données multimédia en temps réel (ce qui est installé sur l’ordinateur local de l’utilisateur final). Autorisent l’ordinateur local de l’utilisateur à utiliser le Skype pour client d’entreprise en cours d’exécution sur le bureau virtuel avec l’un ces deux composants / traitement de V est déplacé sur l’ordinateur local. Pour les environnements de bureau virtuel Citrix, le pack d’optimisation Citrix RealTime est recommandé et une autre prise en charge est prévue.
    
- Le **Pack de la virtualisation VMWare Horizon** Skype pour entreprise, développé en collaboration avec VMWare, vous permet de livrer Skype pour entreprise dans un bureau virtuel tout en offrant une expérience utilisateur satisfaisante. La solution fonctionne grâce à un moteur de média sur le client à créer une solution optimisée, avec le point de terminaison de client media de fournir des fonctions pour les appels audio et vidéo de déchargement. Cette solution qui peut fournir des données audio et vidéo soit directement entre les points de terminaison pour la collaboration en tête-à-tête ou une unité de contrôle Multipoint (MCU) central pour des appels de conférence à plusieurs participants ou les réunions de déchargement.
    
> [!NOTE]
> Le Skype pour 2015 base d’entreprise ou des clients de 2016 ne sont pas pris en charge avec le Pack d’optimisation Citrix HDX en temps réel ou le Pack de la virtualisation VMWare Horizon. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Pack d’optimisation Citrix RealTime
<a name="Citrix_RT"> </a>

Plug-in d’environnement VDI de Citrix (il s’agit d’une fonctionnalité de XenApp et XenDesktop) est compatible avec Lync 2013 et Skype pour entreprise 2015 et 2016 clients (clients complète à l’aide d’un clic pour exécuter le programme d’installation, ou des programmes d’installation MSI publiés après janvier 2017 PU) installés sur un serveur virtuel poste de travail. Son fonctionnement d’ensemble est basé sur le plug-in de Microsoft Lync VDI, mais fonctionne sur un grand nombre de systèmes d’exploitation, y compris les 10 Windows, Macintosh et Linux.
  
Vous trouverez une liste complète des fonctionnalités et technologies prises en charge sur le site Web de Citrix à [l’Offrant de Skype de Microsoft pour les entreprises à XenApp et XenDesktop utilisateurs](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Consultez les liens suivants pour plus d’informations :
  
- Citrix [HDX en temps réel l’optimisation Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Vue d’ensemble technique](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype pour la prise en charge de la fonctionnalité métier](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pack de la virtualisation VMWare Horizon
<a name="Citrix_RT"> </a>

Solution pour environnement VDI de VMWare est compatible avec Skype pour entreprise 2015 et 2016 complète aux clients installé sur un ordinateur de bureau virtuel. Son fonctionnement d’ensemble est basé sur le plug-in de Microsoft Lync VDI, mais fonctionne sur un grand nombre de systèmes d’exploitation, y compris les 10 Windows, Macintosh et Linux. 
  
Vous trouverez une description complète des fonctionnalités et technologies prises en charge sur le site Web de VMWare sur les liens suivants :
  
- [Nouveautés de VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon virtualisation Pack Skype pour entreprise](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Skype de Microsoft pour les entreprises avec Horizon de VMWare](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Avec la solution de plug-in Microsoft Lync VDI, l’utilisateur doit être sur un ordinateur Windows ou un client léger et que le plug-in de Lync VDI de Microsoft pour gérer les flux audio et vidéo à partir du client sur le bureau virtuel. Un utilisateur :
  
1. connectera un périphérique audio/vidéo (par exemple, un casque ou une caméra) à un ordinateur local ;
    
2. Se connecter à un bureau virtuel distant avec Lync 2013 de Skype pour client d’entreprise 2015.
    
3. Entrez les informations d’identification pour Skype pour entreprises sur le bureau virtuel.
    
4. Entrez à nouveau les informations d’identification utilisateur pour établir une connexion avec le plug-in sur l’ordinateur Windows local ou un client léger Lync VDI.
    
Une fois qu’une connexion est établie, l’utilisateur est prêt à effectuer et à recevoir des appels audio et vidéo. Le trafic sur le réseau et la charge sur le bureau virtuel sont minimisés car l’ordinateur local prend en charge le traitement audio/vidéo.
  
Microsoft Lync VDI plug-in est pris en charge uniquement sur certains systèmes d’exploitation Windows et ne prend en charge Lync 2013 ou Skype pour les clients d’entreprise 2015. Consultez la section [Technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt) pour plus de détails sur les technologies prises en charge et les limitations.
  
Consultez les liens suivants pour plus d’informations :
  
- [Technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt)
    
- [Configuration requise pour le plug-in Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Déploiement de la VDI Lync plug-in avec Skype Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Article [CTX138408](https://support.citrix.com/article/CTX138408) de la centre de connaissances Citrix
    
Le plug-in Microsoft VDI est disponible au [plug-in de Microsoft Lync 2013 VDI (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou de [plug-in de Microsoft Lync 2013 VDI (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Ce plug-in est pris en charge avec le Skype pour client d’entreprise 2015, malgré le nom.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Technologies de virtualisation prises en charge et limites connues
<a name="Supported_virt"> </a>

Le plug-in Lync VDI permet d’audio et vidéo d’appel pour les technologies de virtualisation pris en charge. Conformément aux réglementations téléphoniques standard, la prise en charge pour E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation qui sont pris en charge par le plug-in Lync VDI et les limitations de fonctionnalités connues.
  
#### <a name="support-for-virtualization-technologies"></a>Prise en charge des technologies de virtualisation

Le plug-in de VDI Lync prend en charge les sessions à distance complète du bureau dans le scénario de bureau virtuel personnel, mais pas dans le scénario de la session Bureau à distance. Ces scénarios peuvent être décrits comme suit :
  
- **Pris en charge : bureaux virtuels personnalisés ou VDI (Virtual Desktop Infrastructure).** Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer sur le bureau des fichiers qui seront conservés au cours des différentes sessions. Les Services Bureau à distance Microsoft et VMware Horizon de vue sont des implémentations d’exemple qui ont été testées pour une utilisation avec Skype pour entreprise 2015. Les autres implémentations en cours de validation incluent Citrix XenDesktop. Pour plus d’informations sur les environnements VDI spécifiques au fournisseur et le matériel du client qui ont été testés par Microsoft, consultez [l’Infrastructure validés pour Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Non pris en charge : sessions de bureau à distance.** Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Les exemples incluent les Sessions Microsoft du Bureau à distance (RDSH) et Citrix XenApp combiné avec récepteur de Citrix.
    
Le plug-in Lync VDI ne gère pas les autres technologies de virtualisation, tels que la virtualisation d’applications, qui permet l’utilisation d’une application sans nécessiter l’installation de l’application localement. Les exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V). Les modes de diffusion en continu d’application, de mise à distance d’application et de virtualisation mixte (par exemple, mise à distance d’application dans une mise à distance de bureau complet) ne sont pas pris en charge.
  
Le plug-in de VDI Lync a été conçu pour utiliser des API indépendantes de la plate-forme appelés canaux virtuels de dynamique (DVCs). Pour les scénarios qui ne sont pas explicitement pris en charge, reportez-vous à l’assistance du fournisseur de solution VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Configuration requise pour le plug-in Lync VDI
<a name="VDI_prereq"> </a>

Dans un environnement VDI, les ordinateurs virtuels et l’ordinateur local de l’utilisateur doivent répondre aux critères décrits dans cette section.
  
> [!NOTE]
>  Votre fournisseur de solution de virtualisation peut fournir plus d’informations sur l’installation et le déploiement de son environnement. Pour obtenir des informations générales sur le déploiement d’un environnement virtualisé basé sur Hyper-V et les Services Bureau à distance, consultez les articles suivants dans Microsoft TechNet Library : [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Les Services Bureau à distance dans Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Ordinateurs virtuels doivent être configurés avec Windows 8, Windows 7 ou Windows Server 2008 R2 avec les derniers service packs.
  
Ordinateur local de l’utilisateur doit remplir les conditions suivantes :
  
- L’utilisateur doit être hébergé sur Skype pour Business Server 2015 ou Lync Server 2013.
    
- L’ordinateur local doit être en cours d’exécution Windows Embedded Standard 7 avec SP1, Windows 7 SP1 ou Windows 8.
    
- Si vous utilisez des Services Bureau à distance, choisissez le 32 bits ou 64 bits Lync VDI plug-in pour faire correspondre le système d’exploitation de l’ordinateur local. Il n’est pas nécessaire que l’ordinateur local et l’ordinateur virtuel disposent du système d’exploitation 32 ou 64 bits. Si vous utilisez une autre solution ou plate-forme de virtualisation, reportez-vous aux exigences de votre fournisseur.
    
- L’ordinateur doit exécuter la [version la plus récente du client Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032). Installez les dernières mises à jour du client des services Bureau à distance de Microsoft ou le dernier logiciel du client Bureau à distance de votre fournisseur de solutions de virtualisation. 
    
- Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés afin que le son soit lu sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour connexion Bureau à distance dans Windows, consultez la section suivante, « pour configurer les paramètres de connexion Bureau à distance ». 
    
Le plug-in Microsoft VDI est disponible au [plug-in de Microsoft Lync 2013 VDI (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou de [plug-in de Microsoft Lync 2013 VDI (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitations de fonctionnalité connues
<a name="VDI_prereq"> </a>

Les éléments suivants sont connus limitations lorsque vous utilisez le Skype pour client d’entreprise 2015 dans un environnement VDI :
  
Il existe une prise en charge limitée pour les fonctionnalités de délégation d’appel et de réponse groupe Agent Anonymization.
  
Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
  
- pages de réglage des périphériques audio et vidéo intégrés ;
    
- vidéo à vues multiples ;
    
- enregistrement des conversations ;
    
- Participation à des réunions anonyme (c'est-à-dire, jointure Skype pour les réunions d’entreprise hébergées par une entreprise qui ne pas fédérer avec votre organisation).
    
- À l’aide du plug-in avec un périphérique Lync Phone Edition Lync VDI.
    
- continuité des appels en cas de panne du réseau ;
    
- sonneries personnalisées et fonctionnalités d’attente musicale.
    
Le plug-in Lync VDI n’est pas pris en charge dans un environnement Office 365.
  
> [!NOTE]
> Le pack d’optimisation Citrix RealTime prend en charge Office 365. Pour les environnements virtuels basés sur Citrix, examinez la documentation de [Vue d’ensemble technique](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix pour obtenir la liste des fonctionnalités prises en charge et des versions.
  
## <a name="see-also"></a>Voir aussi
<a name="Citrix_RT"> </a>

[Déploiement de la VDI Lync plug-in avec Skype Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

