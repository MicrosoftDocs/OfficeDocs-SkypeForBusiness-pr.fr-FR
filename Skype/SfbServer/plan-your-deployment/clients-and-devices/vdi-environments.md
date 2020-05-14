---
title: Planifier Skype entreprise dans les environnements VDI
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Cette rubrique traite des considérations relatives à la planification de l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: 6886eab8a13db852e0aa86b63d08aa33f82fdaed
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219524"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planifier Skype entreprise dans les environnements VDI
 
Cette rubrique traite des considérations relatives à la planification de l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant. 
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines organisations où les problèmes de sécurité et de conformité sont particulièrement sensibles. Leurs utilisateurs travaillent sur un bureau virtuel avec toutes leurs applications et fichiers de bureau à l’aide des services Bureau à distance ou d’une connexion à distance similaire. Utilisation de Skype entreprise avec l’audio et la vidéo complets sur une connexion telle que nécessite des charges élevées de traitement audio et vidéo sur le client hébergé sur un bureau virtuel. Un logiciel de plug-in VDI supplémentaire est disponible et décharge ce traitement sur l’ordinateur local de l’utilisateur final et réduit la charge sur le bureau virtuel.
  
Trois solutions sont disponibles pour le composant de plug-in VDI, proposé par Microsoft, Citrix ou VMWare. Pour les nouveaux déploiements, Microsoft recommande d’utiliser soit la solution de Pack d’optimisation en temps réel Citrix HDX, soit le Pack de virtualisation de l’horizon VMWare. Le plug-in Lync VDI d’origine est toujours pris en charge pour le reste de son cycle de vie.
  
- Le **plug-in LYNC VDI** a été développé pour Lync 2013 et est compatible avec le client Lync 2013 ou Skype entreprise 2015 exécuté sur un bureau virtuel. Il s’agit d’une application autonome qui s’installe sur l’ordinateur local et permet d’utiliser des périphériques audio et vidéo locaux avec un client sur un bureau virtuel. Le plug-in ne nécessite pas l’installation d’un client Skype entreprise sur l’ordinateur local ou le client léger, qui doit exécuter les systèmes d’exploitation Windows 7, Windows 8 ou Windows Server 2008. (Les périphériques de client léger utilisant ces systèmes d’exploitation et pris en charge par Microsoft incluent : Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 et HP t5740e.) Ce plug-in est toujours pris en charge, mais aucune mise à jour ultérieure n’est planifiée. Pour les environnements virtuels Citrix, le pack d’optimisation Citrix RealTime est recommandé.
    
- Le **Pack d’optimisation en temps réel Citrix** s’appuie sur le plug-in Lync VDI et fonctionne avec les clients Lync 2013 ou Skype entreprise 2016 sur un bureau virtuel. Il a été co-développé par Citrix et Microsoft pour améliorer le plug-in d’origine VDI. Elle peut être installée sur des clients avec des systèmes d’exploitation Windows et autres que Windows (y compris Windows 10, Mac et Linux). Il se compose de deux composants : le connecteur en temps réel (installé sur le bureau virtuel) et le moteur multimédia en temps réel (installé sur l’ordinateur local de l’utilisateur final). Ces deux composants permettent à l’ordinateur local de l’utilisateur d’utiliser le client Skype entreprise s’exécutant sur le bureau virtuel avec le traitement A/V déplacé vers l’ordinateur local. Pour les environnements de bureau virtuels Citrix, le pack d’optimisation Citrix RealTime est recommandé et une prise en charge supplémentaire est prévue.
    
- Le **Pack de virtualisation de l’horizon VMware** pour Skype entreprise, développé en collaboration avec VMware, vous permet de fournir Skype entreprise dans un bureau virtuel tout en offrant une expérience utilisateur exceptionnelle. La solution consiste à exploiter un moteur multimédia sur le client pour créer une solution optimisée, avec le point de terminaison client qui fournit des fonctionnalités de déchargement de médias pour les appels audio et vidéo. Cette solution permet de transmettre des données audio et vidéo directement entre les points de terminaison pour une collaboration en un seul, ou de les décharger dans une unité de contrôle multipoint (MCU) centrale pour les conférences ou les appels de conférence à plusieurs.
    
> [!NOTE]
> Les clients de base Skype entreprise ne sont pas pris en charge avec le pack d’optimisation en temps réel Citrix HDX ou avec le Pack de virtualisation de l’horizon VMWare. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Pack d’optimisation en temps réel Citrix HDX
<a name="Citrix_RT"> </a>

Le plug-in de l’environnement VDI de Citrix (fonctionnalité de XenApp et XenDesktop) est compatible avec Lync 2013 et Skype entreprise 2015 et 2016 (les clients complets utilisent les clients Click pour exécuter le programme d’installation ou les programmes d’installation MSI publiés après les clients de janvier 2017) installés sur un bureau virtuel. Son fonctionnement global repose sur le plug-in Microsoft Lync VDI, mais fonctionne sur un large éventail de systèmes d’exploitation clients, notamment Windows 10, Macintosh et Linux.
  
Vous trouverez une liste complète des fonctionnalités et des technologies prises en charge sur le site Web de Citrix en [proposant les utilisateurs de Microsoft Skype entreprise aux utilisateurs de XenApp et XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Consultez les liens suivants pour plus d’informations :
  
- [HDX du 2,1 Pack d’optimisation en temps réel](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl) Citrix
    
- [Présentation technique](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Prise en charge des fonctionnalités de Skype entreprise CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pack de virtualisation de l’horizon VMWare
<a name="Citrix_RT"> </a>

La solution d’environnement VDI de VMWare est compatible avec les clients complets Skype entreprise 2015 et 2016 installés sur un bureau virtuel. Son fonctionnement global repose sur le plug-in Microsoft Lync VDI, mais fonctionne sur un large éventail de systèmes d’exploitation clients, notamment Windows 10, Macintosh et Linux. 
  
Vous trouverez une description complète des fonctionnalités et des technologies prises en charge sur le site Web VMWare à l’adresse suivante :
  
- [Nouveautés de VMware horizon 7,4 &amp; horizon Client 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pack de virtualisation horizon pour Skype entreprise](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype entreprise avec horizon VMWare](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Avec la solution de plug-in Microsoft Lync VDI, l’utilisateur doit se trouver sur un ordinateur Windows ou un client léger et le plug-in Lync VDI de Microsoft est installé pour gérer les flux audio/vidéo à partir du client sur le bureau virtuel. Un utilisateur doit :
  
1. Connecter un périphérique audio/vidéo (par exemple, un casque ou un appareil photo) à un ordinateur local.
    
2. Connectez-vous à un bureau virtuel distant avec un client Lync 2013 ou Skype entreprise 2015.
    
3. Entrez les informations d’identification de Skype entreprise sur le bureau virtuel.
    
4. Entrez à nouveau les informations d’identification utilisateur pour établir une connexion avec le plug-in Lync VDI sur l’ordinateur Windows local ou le client léger.
    
Une fois qu’une connexion est établie, l’utilisateur est prêt à passer et à recevoir des appels audio et vidéo. Le trafic sur le réseau et la charge sur le bureau virtuel sont minimisés, étant donné que l’ordinateur local gère le traitement audio/vidéo.
  
Le plug-in Lync VDI de Microsoft est uniquement pris en charge sur certains systèmes d’exploitation Windows et ne prend en charge que les clients Lync 2013 ou Skype entreprise 2015. Pour plus d’informations sur les technologies et les limitations prises en charge, voir [technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt) .
  
Consultez les liens suivants pour plus d’informations :
  
- [Technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt)
    
- [Configuration requise pour le plug-in Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Déployer le plug-in Lync VDI avec Skype entreprise Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Article [CTX138408](https://support.citrix.com/article/CTX138408) du centre de connaissances
    
Le plug-in VDI Microsoft est disponible sur le plug-in [Microsoft LYNC vdi 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou le [plug-in microsoft Lync vdi 2013 (64 bits)](https://www.microsoft.com/download/details.aspx?id=35454). Ce plug-in est pris en charge avec le client Skype entreprise 2015, malgré son nom.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Technologies de virtualisation prises en charge et limitations connues
<a name="Supported_virt"> </a>

Le plug-in Lync VDI autorise les appels audio et vidéo pour les technologies de virtualisation prises en charge. Conformément aux réglementations téléphoniques standard, la prise en charge de E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in Lync VDI et les limitations de fonctionnalités connues.
  
#### <a name="support-for-virtualization-technologies"></a>Prise en charge des technologies de virtualisation

Le plug-in Lync VDI prend en charge les sessions de bureau à distance complètes dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session de bureau à distance. Ces scénarios peuvent être décrits comme suit :
  
- **Pris en charge : bureaux virtuels personnalisés ou VDI (Virtual Desktop Infrastructure).** Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer des fichiers sur le bureau qui persistent dans les sessions. Les services Bureau à distance Microsoft et l’affichage horizon VMware sont des exemples d’implémentations qui ont été testées avec Skype entreprise 2015. Les autres implémentations en cours de validation incluent Citrix XenDesktop. Pour plus d’informations sur les environnements VDI et le matériel client spécifiques aux fournisseurs qui ont été testés par Microsoft, voir [infrastructure Qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Non pris en charge : sessions de bureau à distance.** Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Les exemples incluent les sessions Bureau à distance de Microsoft et Citrix XenApp associés au récepteur Citrix.
    
Le plug-in Lync VDI ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation d’application, qui permet l’utilisation d’une application sans avoir à installer entièrement l’application en local. Exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V). La diffusion d’application, l’accès à distance aux applications et les modes de virtualisation mixte (par exemple, application Remoting dans l’accès à distance complet au bureau) ne sont pas pris en charge.
  
Le plug-in Lync VDI a été conçu pour utiliser les API indépendantes des plateformes appelées canaux virtuels dynamiques (DVC). Pour les scénarios qui ne sont pas explicitement pris en charge, reportez-vous aux instructions de prise en charge du fournisseur de solution VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Configuration requise pour le plug-in Lync VDI
<a name="VDI_prereq"> </a>

Dans un environnement VDI, les machines virtuelles et l’ordinateur local de l’utilisateur doivent satisfaire les exigences décrites dans cette section.
  
> [!NOTE]
>  Votre fournisseur de solutions de virtualisation peut fournir des détails sur l’installation et le déploiement de son environnement. Pour obtenir des informations générales sur le déploiement d’un environnement virtualisé basé sur Hyper-V et les services Bureau à distance, reportez-vous aux articles suivants de la bibliothèque Microsoft : [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [services Bureau à distance dans Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Les ordinateurs virtuels doivent être configurés avec Windows 8, Windows 7 ou Windows Server 2008 R2 avec les derniers Service Packs.
  
L’ordinateur local de l’utilisateur doit remplir les conditions suivantes :
  
- L’utilisateur doit être hébergé sur Skype entreprise Server ou Lync Server 2013.
    
- L’ordinateur local doit exécuter Windows Embedded Standard 7 avec SP1, Windows 7 avec SP1 ou Windows 8.
    
- Si vous utilisez les services Bureau à distance, choisissez le plug-in Lync VDI 32 bits ou 64 bits pour qu’il corresponde au système d’exploitation de l’ordinateur local. Il n’est pas nécessaire que l’ordinateur local et l’ordinateur virtuel aient des systèmes d’exploitation 32 bits ou 64 bits. Si vous utilisez une autre solution ou plate-forme de virtualisation, reportez-vous aux exigences de votre fournisseur.
    
- L’ordinateur local doit exécuter la [dernière version du client Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032). Installez les dernières mises à jour du client des services Bureau à distance de Microsoft ou le dernier logiciel client Bureau à distance de votre fournisseur de solutions de virtualisation. 
    
- Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés de manière à ce que l’audio s’exécute sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour la connexion Bureau à distance dans Windows, reportez-vous à la section suivante, « pour configurer les paramètres de la connexion Bureau à distance ». 
    
Le plug-in VDI Microsoft est disponible sur le plug-in [Microsoft LYNC vdi 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou le [plug-in microsoft Lync vdi 2013 (64 bits)](https://www.microsoft.com/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitations des fonctionnalités connues
<a name="VDI_prereq"> </a>

Les limitations suivantes sont connues lorsque vous utilisez le client Skype entreprise 2015 dans un environnement VDI :
  
La prise en charge des fonctionnalités d’anonymisation de l’agent Response Group et de délégation d’appel est limitée.
  
Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
  
- pages de réglage des périphériques audio et vidéo intégrés ;
    
- Vidéo en plusieurs vues.
    
- enregistrement des conversations ;
    
- Participation anonyme à des réunions (c’est-à-dire, participation à des réunions Skype entreprise hébergées par une organisation qui ne se fédérer pas avec votre organisation).
    
- Utilisation du plug-in Lync VDI avec un appareil Lync Phone Edition.
    
- continuité des appels en cas de panne du réseau ;
    
- Sonneries personnalisées et fonctionnalités d’attente musicale.
    
Le plug-in Lync VDI n’est pas pris en charge dans les environnements Microsoft 365 ou Office 365.
  
> [!NOTE]
> Le pack d’optimisation en temps réel Citrix prend en charge Microsoft 365 et Office 365. Pour les environnements virtuels Citrix, consultez la documentation de [Présentation technique](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix pour obtenir la liste des fonctionnalités et des versions prises en charge.
  
## <a name="see-also"></a>Voir aussi
<a name="Citrix_RT"> </a>

[Déployer le plug-in Lync VDI avec Skype entreprise Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

