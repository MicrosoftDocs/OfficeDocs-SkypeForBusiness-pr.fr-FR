---
title: Planifier Skype Entreprise dans des environnements VDI
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Cette rubrique décrit les considérations relatives à la planification de l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: 958c13821eea46be91d51d7399722d2af433ccf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277285"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planifier Skype Entreprise dans des environnements VDI
 
Cette rubrique décrit les considérations relatives à la planification de l’utilisation de Skype entreprise lors de la connexion à un bureau virtuel distant. 
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux. Dans ces entreprises, les utilisateurs effectuent leur travail sur un bureau virtuel avec tous leurs fichiers et applications de bureau à l’aide des services Bureau à distance ou d’une connexion distante similaire. L’utilisation de Skype entreprise avec le son et la vidéo complets sur une connexion telle que l’utilisation de l’audio et de la vidéo sur un ordinateur de bureau virtuel nécessite des chargements importants. Le logiciel enfichable VDI supplémentaire est disponible pour décharger le traitement vers l’ordinateur local de l’utilisateur final et réduire la charge sur le bureau virtuel.
  
Il existe trois solutions disponibles pour le composant enfichable VDI, proposés par Microsoft, Citrix ou VMWare. Pour les nouveaux déploiements, nous vous recommandons d’utiliser la solution HDX en temps réel d’optimisation de Citrix ou le Pack de virtualisation de l’horizon VMWare. Le plug-in Lync VDI d’origine est toujours pris en charge pour le reste de son cycle de vie.
  
- Le **plug-in LYNC VDI** a été développé pour Lync 2013 et est compatible avec le client Lync 2013 ou Skype entreprise 2015 exécuté sur un ordinateur de bureau virtuel. It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop. Le plug-in ne nécessite pas l’installation d’un client Skype entreprise sur l’ordinateur local ou le client léger, lequel doit exécuter les systèmes d’exploitation Windows 7, Windows 8 ou Windows Server 2008. (Les appareils clients légers utilisant ces systèmes d’exploitation et pris en charge par Microsoft sont les suivants: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 et HP t5740e.) Ce plug-in est toujours pris en charge, mais aucune mise à jour ultérieure n’est planifiée. For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.
    
- Le **Pack d’optimisation en temps réel de Citrix** repose sur le plug-in Lync VDI et fonctionne avec Lync 2013 ou les clients Skype entreprise 2016 sur un ordinateur de bureau virtuel. Il a été développé conjointement par Citrix et Microsoft pour offrir des améliorations du plug-in VDI d’origine. Il peut s’installer sur des clients avec des systèmes d’exploitation Windows et non Windows (y compris Windows 10, Mac et Linux). Il comprend deux composants: le connecteur en temps réel (qui est installé sur le bureau virtuel) et le moteur multimédia en temps réel (qui est installé sur l’ordinateur local de l’utilisateur final). Ces deux composants permettent à l’ordinateur local de l’utilisateur d’utiliser le client Skype entreprise exécuté sur le bureau virtuel avec le traitement A/V déplacé vers l’ordinateur local. Pour les environnements de bureau virtuel Citrix, le pack d’optimisation Citrix RealTime est recommandé et une autre prise en charge est prévue.
    
- Le **Pack de virtualisation de l’horizon VMware** pour Skype entreprise, développé en collaboration avec VMware, vous permet d’offrir Skype entreprise sur un ordinateur de bureau virtuel tout en offrant une expérience utilisateur remarquable. La solution fonctionne en tirant parti d’un moteur multimédia sur le client pour créer une solution optimisée, dont le point de terminaison client fournit des fonctionnalités de déchargement de médias pour les appels audio et vidéo. Cette solution capable de transférer de l’audio et de la vidéo directement entre les points de terminaison pour une collaboration en tête-à-tête ou de la décharger sur une unité de contrôle multipoint centralisée (MCU) pour les conférences téléphoniques ou les réunions à plusieurs.
    
> [!NOTE]
> Les clients Skype entreprise basique ne sont pas pris en charge avec le pack d’optimisation de HDX en temps réel de Citrix ou le Pack de virtualisation de l’horizon VMWare. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Pack d’optimisation Citrix RealTime
<a name="Citrix_RT"> </a>

Le plug-in de l’environnement VDI de Citrix (fonctionnalité de XenApp et XenDesktop) est compatible avec Lync 2013 et Skype entreprise 2015 et 2016 (clients complets utilisant un programme d’installation «démarrer en un clic» ou un programme d’installation MSI publiée après le 1er janvier 2017) installé sur un client virtuel D945GBO. Son fonctionnement global est basé sur le plug-in Microsoft Lync VDI, mais fonctionne sur une variété plus large de systèmes d’exploitation clients, y compris Windows 10, Macintosh et Linux.
  
La liste complète des fonctionnalités et des technologies prises en charge est disponible sur le site Web de Citrix dans le cadre de l' [envoi de Microsoft Skype entreprise aux utilisateurs de XenApp et de XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Consultez les liens suivants pour plus d’informations :
  
- [Pack d’optimisation en temps réel HDX 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Présentation technique](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Prise en charge de la fonctionnalité Skype entreprise CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pack de virtualisation de l’horizon VMWare
<a name="Citrix_RT"> </a>

La solution de l’environnement VDI de VMWare est compatible avec Skype entreprise 2015 et 2016 clients complets installés sur un ordinateur de bureau virtuel. Son fonctionnement global est basé sur le plug-in Microsoft Lync VDI, mais fonctionne sur une variété plus large de systèmes d’exploitation clients, y compris Windows 10, Macintosh et Linux. 
  
Une description complète des fonctionnalités et des technologies prises en charge est disponible sur le site Web de VMWare aux liens suivants:
  
- [Nouveautés de VMware horizon 7,4 &amp; horizon client 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pack de virtualisation horizon pour Skype entreprise](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype entreprise avec un horizon VMWare](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Dans le module enfichable Microsoft Lync VDI, l’utilisateur doit se trouver sur un ordinateur ou un client léger Windows et disposer du plug-in Lync VDI de Microsoft installé pour gérer les flux audio et vidéo du client sur le bureau virtuel. Un utilisateur :
  
1. connectera un périphérique audio/vidéo (par exemple, un casque ou une caméra) à un ordinateur local ;
    
2. Connectez-vous à un bureau virtuel distant avec un client 2015 Lync 2013 ou Skype entreprise.
    
3. Entrez les informations d’identification pour Skype entreprise sur le bureau virtuel.
    
4. Entrez à nouveau les informations d’identification de l’utilisateur pour établir une connexion avec le plug-in Lync VDI sur l’ordinateur Windows local ou le client léger.
    
Une fois qu’une connexion est établie, l’utilisateur est prêt à effectuer et à recevoir des appels audio et vidéo. Le trafic sur le réseau et la charge sur le bureau virtuel sont minimisés car l’ordinateur local prend en charge le traitement audio/vidéo.
  
Le plug-in Lync VDI de Microsoft est uniquement pris en charge sur certains systèmes d’exploitation Windows et ne prend en charge que Lync 2013 ou les clients Skype entreprise 2015. Consultez la section [Technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt) pour plus de détails sur les technologies prises en charge et les limitations.
  
Consultez les liens suivants pour plus d’informations :
  
- [Technologies de virtualisation prises en charge et limitations connues](vdi-environments.md#Supported_virt)
    
- [Configuration requise pour le plug-in Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Déploiement du plug-in Lync VDI avec Skype entreprise Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Centre de connaissances de Citrix-article [CTX138408](https://support.citrix.com/article/CTX138408)
    
Le plug-in Microsoft VDI est disponible sur le plug-in [Microsoft LYNC vdi 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou sur le [plug-in Lync vdi 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Ce plug-in est pris en charge avec le client Skype entreprise 2015, malgré son nom.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Technologies de virtualisation prises en charge et limites connues
<a name="Supported_virt"> </a>

Le plug-in Lync VDI autorise les appels audio et vidéo pour les technologies de virtualisation prises en charge. Conformément aux réglementations téléphoniques standard, la prise en charge pour E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in Lync VDI et les limitations de fonctionnalités connues.
  
#### <a name="support-for-virtualization-technologies"></a>Prise en charge des technologies de virtualisation

Le plug-in Lync VDI prend en charge les sessions complètes distantes du bureau dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session Bureau à distance. Ces scénarios peuvent être décrits comme suit :
  
- **Pris en charge : bureaux virtuels personnalisés ou VDI (Virtual Desktop Infrastructure).** Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer sur le bureau des fichiers qui seront conservés au cours des différentes sessions. Le mode d’affichage des services Bureau à distance Microsoft et de l’horizon VMware s’utilise dans des exemples d’implémentation qui ont été testés pour Skype entreprise 2015. Les autres implémentations en cours de validation incluent Citrix XenDesktop. Pour plus d’informations sur les environnements VDI spécifiques aux fournisseurs et sur le matériel client testés par Microsoft, voir [infrastructure Qualified pour Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Non pris en charge : sessions de bureau à distance.** Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Par exemple, les sessions de bureau à distance Microsoft et Citrix XenApp combinés avec le destinataire Citrix.
    
Le plug-in Lync VDI ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation de l’application, qui permet d’utiliser une application sans avoir besoin d’installer entièrement l’application en local. Les exemples d’implémentations incluent Citrix XenApp et Microsoft Application Virtualization (App-V). Les modes de diffusion en continu d’application, de mise à distance d’application et de virtualisation mixte (par exemple, mise à distance d’application dans une mise à distance de bureau complet) ne sont pas pris en charge.
  
Le plug-in Lync VDI a été conçu pour utiliser des API indépendantes de la plateforme appelées canaux virtuels dynamiques (DVCs). Pour les scénarios qui ne sont pas explicitement pris en charge, reportez-vous à l’assistance du fournisseur de solution VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Configuration requise pour le plug-in Lync VDI
<a name="VDI_prereq"> </a>

Dans un environnement VDI, les machines virtuelles et l’ordinateur local de l’utilisateur doivent respecter les exigences indiquées dans cette section.
  
> [!NOTE]
>  Votre fournisseur de solution de virtualisation peut fournir plus d’informations sur l’installation et le déploiement de son environnement. Pour obtenir des informations générales sur le déploiement d’un environnement virtualisé basé sur Hyper-V et sur les services Bureau à distance, consultez les articles suivants dans Microsoft Library: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [services Bureau à distance dans Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Les machines virtuelles doivent être configurées avec Windows 8, Windows 7 ou Windows Server 2008 R2 avec les derniers Service Packs.
  
L’ordinateur local de l’utilisateur doit présenter la configuration suivante:
  
- L’utilisateur doit être hébergé sur Skype entreprise Server ou Lync Server 2013.
    
- L’ordinateur local doit exécuter Windows Embedded Standard 7 avec SP1, Windows 7 avec SP1 ou Windows 8.
    
- Si vous utilisez les services Bureau à distance, sélectionnez le plug-in Lync VDI 32-bit ou 64 bits pour correspondre au système d’exploitation de l’ordinateur local. Il n’est pas nécessaire que l’ordinateur local et l’ordinateur virtuel disposent du système d’exploitation 32 ou 64 bits. Si vous utilisez une autre solution ou plate-forme de virtualisation, reportez-vous aux exigences de votre fournisseur.
    
- L’ordinateur local doit exécuter la [version la plus récente du client de bureau à distance](https://go.microsoft.com/fwlink/p/?LinkId=268032). Installez les dernières mises à jour du client des services Bureau à distance de Microsoft ou le dernier logiciel du client Bureau à distance de votre fournisseur de solutions de virtualisation. 
    
- Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés afin que le son soit lu sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour la connexion Bureau à distance dans Windows, reportez-vous à la section «pour configurer les paramètres de connexion Bureau à distance». 
    
Le plug-in Microsoft VDI est disponible sur le plug-in [Microsoft LYNC vdi 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou sur le [plug-in Lync vdi 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitations de fonctionnalité connues
<a name="VDI_prereq"> </a>

Vous trouverez ci-après des limitations connues lorsque vous utilisez le client Skype entreprise 2015 dans un environnement VDI:
  
La prise en charge des fonctionnalités de délégation d’appel et d’anonymisation de l’agent de Response Group est limitée.
  
Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
  
- pages de réglage des périphériques audio et vidéo intégrés ;
    
- vidéo à vues multiples ;
    
- enregistrement des conversations ;
    
- La participation anonyme aux réunions (c’est-à-dire, la participation à des réunions Skype entreprise hébergées par une organisation non fédérée avec votre organisation).
    
- Utiliser le plug-in Lync VDI avec un appareil Lync Phone Edition.
    
- continuité des appels en cas de panne du réseau ;
    
- sonneries personnalisées et fonctionnalités d’attente musicale.
    
Le plug-in Lync VDI n’est pas pris en charge dans un environnement Office 365.
  
> [!NOTE]
> Le pack d’optimisation Citrix RealTime prend en charge Office 365. En environnement virtuel Citrix, consultez la documentation de la [Présentation technique](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix pour obtenir la liste des fonctionnalités et versions prises en charge.
  
## <a name="see-also"></a>Voir aussi
<a name="Citrix_RT"> </a>

[Déploiement du plug-in Lync VDI avec Skype entreprise Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

