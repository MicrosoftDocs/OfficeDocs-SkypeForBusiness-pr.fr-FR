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
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Cette rubrique décrit les considérations de planification pour l’aide de Skype pour les entreprises lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: 978a93f91ae985302d2b02d226dee4c1ddb476b7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883872"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planifier Skype Entreprise dans des environnements VDI
 
Cette rubrique décrit les considérations de planification pour l’aide de Skype pour les entreprises lors de la connexion à un bureau virtuel distant. 
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux. Dans ces entreprises, les utilisateurs effectuent leur travail sur un bureau virtuel avec tous leurs fichiers et applications de bureau à l’aide des services Bureau à distance ou d’une connexion distante similaire. À l’aide de Skype pour les entreprises avec complète audio et vidéo sur une connexion en procédant nécessitent des charges de l’audio et vidéo de traitement sur le client hébergés sur un bureau virtuel. Logiciel de plug-in VDI supplémentaire n’est disponible que décharge le traitement à l’ordinateur local de l’utilisateur final et réduit la charge sur le bureau virtuel.
  
Il existe trois solutions pour le composant de plug-in VDI, offert par Microsoft, Citrix ou VMWare. Pour les nouveaux déploiements, Microsoft recommande l’utilisation de la solution du Pack d’optimisation Citrix HDX en temps réel ou le Pack de virtualisation VMWare Horizon. Le plug-in de VDI Lync d’origine est toujours pris en charge pour le reste de son cycle de vie.
  
- Le **Lync VDI plug-in** a été développé pour Lync 2013 et est compatible avec Skype ou Lync 2013 pour le client Business 2015 s’exécutant sur un bureau virtuel. Il s’agit d’une application autonome qui s’installe sur l’ordinateur local et permet d’utiliser des périphériques audio et vidéo locaux avec un client sur un bureau virtuel. Le plug-in ne nécessite pas une Skype pour client d’entreprise doit être installé sur l’ordinateur local ou d’un client léger qui doit s’exécuter des systèmes d’exploitation Windows 7, Windows 8 ou Windows Server 2008. (Les périphériques client léger à l’aide de ces systèmes d’exploitation et la prise en charge par Microsoft incluent : Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, t610 HP et HP t5740e.) Ce plug-in est toujours prise en charge, mais aucun futures mises à jour ne sont planifiées. Pour les environnements virtuels Citrix, le pack d’optimisation Citrix RealTime est recommandé.
    
- Le **Pack d’optimisation en temps réel Citrix** s’appuie sur le plug-in Lync VDI et fonctionne avec Lync 2013 ou Skype pour les clients professionnels 2016 sur un bureau virtuel. Il a été développé conjointement par Citrix et Microsoft pour offrir des améliorations du plug-in VDI d’origine. Il peut s’installer sur des clients avec des systèmes d’exploitation Windows et non Windows (y compris Windows 10, Mac et Linux). Il se compose de deux composants : le connecteur en temps réel (qui est installé sur le bureau virtuel) et le moteur de médias en temps réel (qui est installé sur l’ordinateur local de l’utilisateur final). Ces deux composants autoriser l’ordinateur local de l’utilisateur à utiliser le Skype pour client d’entreprise en cours d’exécution sur le bureau virtuel avec A / traitement V déplacé sur l’ordinateur local. Pour les environnements de bureau virtuel Citrix, le pack d’optimisation Citrix RealTime est recommandé et une autre prise en charge est prévue.
    
- Le **Pack de virtualisation VMWare Horizon** Skype pour les entreprises, développé en collaboration avec VMWare, vous permet de remettre Skype pour les entreprises dans un bureau virtuel tout en offrant une expérience utilisateur satisfaisante. La solution fonctionne grâce à un moteur de média au niveau du client pour créer une solution optimisée, avec le point de terminaison client fournissant multimédia déchargement de fonctionnalités pour les appels audio et vidéos. Cette solution qui peut fournir des données audio et vidéo soit directement entre les points de terminaison pour la collaboration en tête-à-tête, ou une unité de contrôle Multipoint (MCU) central pour des appels de conférence ou des réunions de déchargement.
    
> [!NOTE]
> Le Skype pour les clients professionnels base ne sont pas pris en charge avec le Pack d’optimisation Citrix HDX en temps réel ou le Pack de virtualisation VMWare Horizon. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Pack d’optimisation Citrix RealTime
<a name="Citrix_RT"> </a>

Plug-in d’environnement VDI de Citrix (il s’agit d’une fonctionnalité de XenApp et XenDesktop) est compatible avec Lync 2013 et Skype pour Business 2015 et 2016 clients (clients complète à l’aide d’un clic pour exécuter le programme d’installation ou des programmes d’installation MSI publiés après janvier 2017 mise à jour publique) installés sur un serveur virtuel bureau. Son fonctionnement global est basé sur le plug-in Microsoft Lync VDI, mais fonctionne sur un grand nombre de systèmes d’exploitation, y compris les 10 Windows, Macintosh et Linux.
  
Vous trouverez la liste complète des fonctionnalités et les technologies prises en charge sur le site Web de Citrix à [Proposer Microsoft Skype pour les entreprises et les utilisateurs XenDesktop XenApp](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Consultez les liens suivants pour plus d’informations :
  
- Citrix [HDX en temps réel optimisation Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Vue d’ensemble technique](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype pour la prise en charge de la fonctionnalité Business](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pack de virtualisation VMWare Horizon
<a name="Citrix_RT"> </a>

Solution d’environnement VMWare VDI est compatible avec Skype pour Business 2015 et 2016 clients complètes installés sur un bureau virtuel. Son fonctionnement global est basé sur le plug-in Microsoft Lync VDI, mais fonctionne sur un grand nombre de systèmes d’exploitation, y compris les 10 Windows, Macintosh et Linux. 
  
Vous trouverez une description complète des fonctionnalités et les technologies prises en charge sur le site Web VMWare les liens suivants :
  
- [Nouveautés de l’Horizon VMware 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pack de virtualisation horizon de Skype pour les entreprises](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Skype de Microsoft pour les entreprises avec VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

La solution plug-in Microsoft Lync VDI, l’utilisateur doit se trouver sur un ordinateur Windows ou un client léger et disposer du plug-in Lync VDI de Microsoft pour gérer les flux audio/vidéo à partir du client sur le bureau virtuel. Un utilisateur :
  
1. connectera un périphérique audio/vidéo (par exemple, un casque ou une caméra) à un ordinateur local ;
    
2. Se connecter à un bureau virtuel à distance avec Skype de Lync 2013 pour le client Business 2015.
    
3. Entrez les informations d’identification sur le bureau virtuel Skype pour les entreprises.
    
4. Entrez les informations d’identification utilisateur pour établir une connexion avec le Lync VDI plug-in sur l’ordinateur Windows local ou un client léger.
    
Une fois qu’une connexion est établie, l’utilisateur est prêt à effectuer et à recevoir des appels audio et vidéo. Le trafic sur le réseau et la charge sur le bureau virtuel sont minimisés car l’ordinateur local prend en charge le traitement audio/vidéo.
  
Microsoft Lync VDI plug-in est uniquement pris en charge sur certains systèmes d’exploitation Windows et ne prend en charge Lync 2013 ou Skype pour les clients professionnels 2015. Consultez la section [Technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt) pour plus de détails sur les technologies prises en charge et les limitations.
  
Consultez les liens suivants pour plus d’informations :
  
- [Technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt)
    
- [Configuration requise pour le plug-in Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Déployer le Lync VDI plug-in avec Skype pour Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Article du centre de la base de connaissances Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
Le plug-in VDI Microsoft est disponible sur [Microsoft Lync 2013 VDI plug-in (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou [Microsoft Lync 2013 VDI plug-in (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Ce plug-in est pris en charge avec la Skype pour client Business 2015, malgré le nom.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Technologies de virtualisation prises en charge et limites connues
<a name="Supported_virt"> </a>

Le plug-in Lync VDI permet audio et vidéo d’appel pour les technologies de virtualisation pris en charge. Conformément aux réglementations téléphoniques standard, la prise en charge pour E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation sont pris en charge par le plug-in Lync VDI et les limitations connues de fonctionnalité.
  
#### <a name="support-for-virtualization-technologies"></a>Prise en charge des technologies de virtualisation

Le plug-in Lync VDI prend en charge les sessions distantes plein dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session Bureau à distance. Ces scénarios peuvent être décrits comme suit :
  
- **Pris en charge : bureaux virtuels personnalisés ou VDI (Virtual Desktop Infrastructure).** Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer sur le bureau des fichiers qui seront conservés au cours des différentes sessions. Services Bureau à distance Microsoft et VMware Horizon affichage sont des implémentations d’exemple qui ont été testées pour une utilisation avec Skype pour Business 2015. Les autres implémentations en cours de validation incluent Citrix XenDesktop. Pour plus d’informations sur les environnements VDI spécifiques au fournisseur et le matériel client ont été testés par Microsoft, consultez [Infrastructure qualifiés pour Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Non pris en charge : sessions de bureau à distance.** Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Exemples de Sessions Microsoft du Bureau à distance (distance) et Citrix XenApp combinées avec Citrix récepteur.
    
Le plug-in Lync VDI ne prend pas en charge autres technologies de virtualisation, telles que la virtualisation d’applications, qui permet l’utilisation d’une application sans exiger l’installation de l’application localement. Les exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V). Les modes de diffusion en continu d’application, de mise à distance d’application et de virtualisation mixte (par exemple, mise à distance d’application dans une mise à distance de bureau complet) ne sont pas pris en charge.
  
Le plug-in Lync VDI a été conçu pour utiliser les API indépendant de la plate-forme appelées dynamique virtuel canaux (DVCs). Pour les scénarios qui ne sont pas explicitement pris en charge, reportez-vous à l’assistance du fournisseur de solution VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Configuration requise pour le plug-in Lync VDI
<a name="VDI_prereq"> </a>

Dans un environnement VDI, les ordinateurs virtuels et l’ordinateur local de l’utilisateur doivent remplir les conditions décrites dans cette section.
  
> [!NOTE]
>  Votre fournisseur de solution de virtualisation peut fournir plus d’informations sur l’installation et le déploiement de son environnement. Pour des informations générales sur le déploiement d’un environnement virtualisé basé sur Hyper-V et les Services Bureau à distance, voir les articles suivants dans Microsoft Library : [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Les Services Bureau à distance dans Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Machines virtuelles doit être configurés avec Windows 8, Windows 7 ou Windows Server 2008 R2 avec les service packs les plus récentes.
  
Ordinateur local de l’utilisateur doit remplir les conditions suivantes :
  
- L’utilisateur doit être hébergé sur Skype pour Business Server ou Microsoft Lync Server 2013.
    
- L’ordinateur local doit exécuter Windows Embedded Standard 7 avec SP1, Windows 7 avec SP1 ou Windows 8.
    
- Si vous utilisez des Services Bureau à distance, choisissez le 32 bits ou 64 bits Lync VDI plug-in pour la correspondance de système d’exploitation de l’ordinateur local. Il n’est pas nécessaire que l’ordinateur local et l’ordinateur virtuel disposent du système d’exploitation 32 ou 64 bits. Si vous utilisez une autre solution ou plate-forme de virtualisation, reportez-vous aux exigences de votre fournisseur.
    
- L’ordinateur local doit exécuter la [version la plus récente du client Bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032). Installez les dernières mises à jour du client des services Bureau à distance de Microsoft ou le dernier logiciel du client Bureau à distance de votre fournisseur de solutions de virtualisation. 
    
- Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés afin que le son soit lu sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour la connexion Bureau à distance dans Windows, voir la section suivante, « pour configurer les paramètres de connexion Bureau à distance ». 
    
Le plug-in VDI Microsoft est disponible sur [Microsoft Lync 2013 VDI plug-in (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou [Microsoft Lync 2013 VDI plug-in (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitations de fonctionnalité connues
<a name="VDI_prereq"> </a>

Les éléments suivants sont limites connues lorsque vous utilisez le Skype pour Business 2015 client dans un environnement VDI :
  
Il est prise en charge limitée pour les fonctionnalités de délégation d’appel et d’anonymisation d’Agent de Response Group.
  
Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
  
- pages de réglage des périphériques audio et vidéo intégrés ;
    
- vidéo à vues multiples ;
    
- enregistrement des conversations ;
    
- Participation à des réunions anonymement (c'est-à-dire participation Skype pour les réunions Business hébergées par une organisation qui n’est pas fédérée avec votre organisation).
    
- À l’aide du Lync plug-in VDI avec un périphérique Lync Phone Edition.
    
- continuité des appels en cas de panne du réseau ;
    
- sonneries personnalisées et fonctionnalités d’attente musicale.
    
Le plug-in Lync VDI n’est pas pris en charge dans un environnement Office 365.
  
> [!NOTE]
> Le pack d’optimisation Citrix RealTime prend en charge Office 365. Pour les environnements virtuels basée sur Citrix, consulter la documentation de [Vue d’ensemble technique](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix pour la liste des fonctionnalités prises en charge et des versions.
  
## <a name="see-also"></a>Voir aussi
<a name="Citrix_RT"> </a>

[Déployer le Lync VDI plug-in avec Skype pour Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

