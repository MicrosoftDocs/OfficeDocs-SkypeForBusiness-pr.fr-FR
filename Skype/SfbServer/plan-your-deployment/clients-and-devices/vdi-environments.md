---
title: Planifier les Skype Entreprise dans les environnements VDI
author: cichur
ms.author: v-cichur
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Cette rubrique traite des considérations de planification pour l’utilisation Skype Entreprise lors de la connexion à un bureau virtuel distant.
ms.openlocfilehash: 7b169db870ad652dcf8b64552d9351e47e7117bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621010"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planifier les Skype Entreprise dans les environnements VDI
 
Cette rubrique traite des considérations de planification pour l’utilisation Skype Entreprise lors de la connexion à un bureau virtuel distant. 
  
Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines organisations où les problèmes de sécurité et de conformité sont particulièrement sensibles. Leurs utilisateurs font leur travail sur un bureau virtuel avec toutes leurs applications et fichiers de bureau à l’aide des services Bureau à distance ou d’une connexion distante similaire. L Skype Entreprise’utilisation de l’audio et de la vidéo complètes sur une connexion de ce genre nécessite de nombreuses charges de traitement audio et vidéo sur le client sur un bureau virtuel. Un logiciel de plug-in VDI supplémentaire est disponible, qui décharge ce traitement sur l’ordinateur local de l’utilisateur final et réduit la charge sur le bureau virtuel.
  
Trois solutions sont disponibles pour le composant de plug-in VDI, proposées par Microsoft, Citrix ou VMWare. Pour les nouveaux déploiements, Microsoft recommande d’utiliser la solution Citrix HDX RealTime Optimization Pack ou VMWare Horizon Virtualization Pack. Le plug-in VDI Lync d’origine est toujours pris en charge pour le restant de son cycle de vie.
  
- Le **plug-in Lync VDI** a été développé pour Lync 2013 et est compatible avec le client Lync 2013 ou Skype Entreprise 2015 s’exécutant sur un bureau virtuel. Il s’agit d’une application autonome qui s’installe sur l’ordinateur local et permet d’utiliser des périphériques audio et vidéo locaux avec un client sur un bureau virtuel. Le plug-in ne nécessite pas l’installation d’un client Skype Entreprise sur l’ordinateur local ou le client léger, qui doit exécuter les systèmes d’exploitation Windows 7, Windows 8 ou Windows Server 2008. (Les appareils clients légers utilisant ces systèmes d’exploitation et pris en charge par Microsoft sont les suivants : Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 et HP t5740e.) Ce plug-in est toujours pris en charge, mais aucune mise à jour future n’est planifiée. Pour les environnements virtuels Citrix, le pack d’optimisation Citrix RealTime est recommandé.
    
- Le pack **d’optimisation Citrix RealTime** s’appuie sur le plug-in Lync VDI et fonctionne avec les clients Lync 2013 ou Skype Entreprise 2016 sur un bureau virtuel. Il a été co-développé par Citrix et Microsoft pour améliorer le plug-in VDI d’origine. Il peut être installé sur des clients avec des systèmes Windows et non Windows (y compris Windows 10, Mac et Linux). Il se compose de deux composants : le connecteur RealTime (qui est installé sur le bureau virtuel) et le moteur RealTime Media (qui est installé sur l’ordinateur local de l’utilisateur final). Ces deux composants permettent à l’ordinateur local de l’utilisateur d’utiliser le client Skype Entreprise s’exécutant sur le bureau virtuel avec le traitement A/V déplacé vers l’ordinateur local. Pour les environnements de bureau virtuel Citrix, le pack d’optimisation Citrix RealTime est recommandé et une prise en charge supplémentaire est planifiée.
    
- Le pack **VMWare Horizon Virtualization Pack** pour Skype Entreprise, développé en collaboration avec VMWare, vous permet de fournir des Skype Entreprise dans un bureau virtuel tout en offrent une expérience utilisateur réussie. La solution fonctionne en tirant parti d’un moteur multimédia sur le client pour créer une solution optimisée, avec le point de terminaison client fournissant des fonctionnalités de déchargement multimédia pour les appels audio et vidéo. Cette solution qui peut fournir de l’audio et de la vidéo soit directement entre les points de terminaison pour une collaboration un-à-un, soit la décharger vers une unité centrale de contrôle multipoint (MCU) pour les conférences ou réunions à plusieurs.
    
> [!NOTE]
> Les clients Skype Entreprise de base ne sont pas pris en charge avec citrix HDX RealTime Optimization Pack ou VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Pack d’optimisation Citrix HDX RealTime
<a name="Citrix_RT"> </a>

Le plug-in d’environnement VDI de Citrix (une fonctionnalité de XenApp et XenDesktop) est compatible avec les clients Lync 2013 et Skype Entreprise 2015 et 2016 (clients complets utilisant un clic pour exécuter le programme d’installation, ou les installers MSI publiés après la mise à jour publique de janvier 2017) installés sur un bureau virtuel. Son fonctionnement global repose sur le plug-in Microsoft Lync VDI, mais fonctionne sur un plus grand nombre de systèmes d’exploitation clients, notamment Windows 10, Macintosh et Linux.
  
Vous pouvez trouver la liste complète des fonctionnalités et technologies pris en charge sur le site Web Citrix à l’adresse [Delivering Microsoft Skype Entreprise to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Pour plus d’informations, ez les liens suivants :
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Vue d’ensemble technique](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Prise en charge des fonctionnalités Skype Entreprise CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

La solution d’environnement VDI de VMWare est compatible avec Skype Entreprise 2015 et 2016 Les clients complets sont installés sur un bureau virtuel. Son fonctionnement global repose sur le plug-in Microsoft Lync VDI, mais fonctionne sur un plus grand nombre de systèmes d’exploitation clients, notamment Windows 10, Macintosh et Linux. 
  
Vous pouvez trouver une discussion complète des fonctionnalités et des technologies pris en charge sur le site web VMWare à l’aide des liens suivants :
  
- [Nouveautés de VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pack de virtualisation Horizon pour Skype Entreprise](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype Entreprise avec VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Avec la solution de plug-in Microsoft Lync VDI, l’utilisateur doit se trouver sur un ordinateur Windows ou un client léger et installer le plug-in Lync VDI de Microsoft pour gérer les flux audio/vidéo du client sur le bureau virtuel. Un utilisateur :
  
1. Connecter un périphérique audio/vidéo (comme un casque ou un appareil photo) sur un ordinateur local.
    
2. Connecter sur un bureau virtuel distant avec un client Lync 2013 Skype Entreprise 2015.
    
3. Entrez les informations d’identification Skype Entreprise sur le bureau virtuel.
    
4. Entrez de nouveau les informations d’identification de l’utilisateur pour établir une connexion avec le plug-in Lync VDI sur l’ordinateur Windows client léger ou local.
    
Une fois la connexion établie, l’utilisateur est prêt à passer et recevoir des appels audio et vidéo. Le trafic sur le réseau et la charge sur le bureau virtuel sont réduits, car l’ordinateur local gère le traitement audio/vidéo.
  
Le plug-in Lync VDI de Microsoft est uniquement pris en charge sur certains systèmes d’exploitation Windows et prend uniquement en charge les clients Lync 2013 Skype Entreprise 2015. Voir technologies de virtualisation pris en charge [et limitations connues](vdi-environments.md#Supported_virt) pour plus d’informations sur les technologies et limitations pris en charge.
  
Pour plus d’informations, ez les liens suivants :
  
- [Technologies de virtualisation et limitations connues pris en charge](vdi-environments.md#Supported_virt)
    
- [Conditions préalables pour le plug-in Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Déployer le plug-in Lync VDI avec Skype Entreprise Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Article du Centre de connaissances Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
Le plug-in Microsoft VDI est disponible dans le plug-in [Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou plug-in [Microsoft Lync VDI 2013 (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454) Ce plug-in est pris en charge avec le client Skype Entreprise 2015, malgré son nom.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Technologies de virtualisation et limitations connues pris en charge
<a name="Supported_virt"> </a>

Le plug-in Lync VDI permet l’appel audio et vidéo pour les technologies de virtualisation prises en charge. Conformément aux réglementations téléphoniques standard, la prise en charge du service E911 est également incluse. Les sections suivantes décrivent les technologies de virtualisation prises en charge par le plug-in Lync VDI et les limitations de fonctionnalité connues.
  
#### <a name="support-for-virtualization-technologies"></a>Prise en charge des technologies de virtualisation

Le plug-in Lync VDI prend en charge les sessions de bureau à distance complètes dans le scénario de bureau virtuel personnel, mais pas dans le scénario de session bureau à distance. Ces scénarios peuvent être décrits comme suit :
  
- **Pris en charge : bureaux virtuels personnalisés ou infrastructure VDI (Virtual Desktop Infrastructure).** Dans ce scénario, chaque utilisateur se connecte à un bureau virtuel personnalisable et peut enregistrer des fichiers sur le bureau qui persistent entre les sessions. Bureau à distance Microsoft Les services et VMware Horizon View sont des exemples d’implémentations qui ont été testées pour être Skype Entreprise 2015. Citrix XenDesktop est une autre implémentation en cours de validation. Pour plus d’informations sur les environnements VDI propres au fournisseur et le matériel client qui ont été testés par Microsoft, voir Infrastructure qualifiée [pour Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).
    
- **Non pris en charge : sessions Bureau à distance.** Dans ce scénario, chaque utilisateur se connecte à une session de bureau virtuel générique qui ne peut pas être personnalisée. Par exemple, Bureau à distance Microsoft sessions de chiffrement (RDSH) et Citrix XenApp combinées avec Citrix Receiver.
    
Le plug-in Lync VDI ne prend pas en charge les autres technologies de virtualisation, telles que la virtualisation d’application, qui permet l’utilisation d’une application sans nécessiter l’installation locale de l’application complète. Citrix XenApp et Microsoft Application Virtualization (App-V) sont des exemples d’implémentations. Les modes de diffusion en continu d’application, d’accès à la remoting d’application et de virtualisation mixte (par exemple, la mise à l’accès à la ligne à l’aide d’une technologie à remoting de bureau complet) ne sont pas pris en charge.
  
Le plug-in Lync VDI a été conçu pour utiliser des API indépendantes de la plateforme appelées canaux virtuels dynamiques (DVCs). Pour les scénarios qui ne sont pas explicitement pris en charge, reportez-vous aux instructions de support du fournisseur de solutions VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Conditions préalables pour le plug-in Lync VDI
<a name="VDI_prereq"> </a>

Dans un environnement VDI, les ordinateurs virtuels et l’ordinateur local de l’utilisateur doivent répondre aux exigences décrites dans cette section.
  
> [!NOTE]
>  Votre fournisseur de solutions de virtualisation peut fournir des détails sur l’installation et le déploiement de son environnement. Pour obtenir des informations générales sur le déploiement d’un environnement virtualisé basé sur Hyper-V et les services Bureau à distance, voir les articles suivants dans la bibliothèque Microsoft : [Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10)), Services Bureau à distance dans [Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10)) 
  
Les ordinateurs virtuels doivent être configurés avec Windows 8, Windows 7 ou Windows Server 2008 R2 avec les Derniers Service Packs.
  
L’ordinateur local de l’utilisateur doit répondre aux exigences suivantes :
  
- L’utilisateur doit être Skype Entreprise Server ou Lync Server 2013.
    
- L’ordinateur local doit être Windows embedded Standard 7 avec SP1, Windows 7 avec SP1 ou Windows 8.
    
- Si vous utilisez les services Bureau à distance, choisissez le plug-in Lync VDI 32 bits ou 64 bits pour correspondre au système d’exploitation de l’ordinateur local. Il n’est pas nécessaire que l’ordinateur local et la machine virtuelle ont des systèmes d’exploitation 32 bits ou 64 bits. Si vous utilisez une autre solution ou plateforme de virtualisation, reportez-vous aux exigences de votre fournisseur.
    
- L’ordinateur local doit être en cours d’exécution [de la dernière version du client bureau à distance.](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients) Installez les dernières mises à jour du client Des services Bureau à distance à partir de Microsoft ou le dernier logiciel client bureau à distance à partir de votre fournisseur de solutions de virtualisation. 
    
- Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés pour que l’audio soit l’écoute sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour la connexion Bureau à distance dans Windows, consultez la section suivante, « Pour configurer les paramètres de connexion Bureau à distance ». 
    
Le plug-in Microsoft VDI est disponible dans le plug-in [Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) ou plug-in [Microsoft Lync VDI 2013 (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454)
  
#### <a name="known-feature-limitations"></a>Limitations connues des fonctionnalités
<a name="VDI_prereq"> </a>

Les limitations connues sont les suivantes lorsque vous utilisez le client Skype Entreprise 2015 dans un environnement VDI :
  
La prise en charge des fonctionnalités de délégation d’appel et d’anonymisation de l’agent Response Group est limitée.
  
Il n’existe pas de prise en charge pour les fonctionnalités suivantes :
  
- pages de réglage des périphériques audio et vidéo intégrés ;
    
- Vidéo à affichage multiple.
    
- enregistrement des conversations ;
    
- Participer à des réunions de manière anonyme (c’est-à-dire rejoindre Skype Entreprise réunions hébergées par une organisation qui ne se fédérera pas avec votre organisation).
    
- Utilisation du plug-in Lync VDI avec un appareil Lync Téléphone Edition.
    
- continuité des appels en cas de panne du réseau ;
    
- Sonneries personnalisées et fonctionnalités d’attente musicale.
    
Le plug-in Lync VDI n’est pas pris en charge dans Microsoft 365 ou Office 365 environnements.
  
> [!NOTE]
> Le pack d’optimisation Citrix RealTime prend en charge Microsoft 365 et Office 365. Pour les environnements virtuels Citrix, examinez la documentation [De](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) présentation technique de Citrix pour obtenir la liste des fonctionnalités et versions pris en charge.
  
## <a name="see-also"></a>Voir aussi
<a name="Citrix_RT"> </a>

[Déployer le plug-in Lync VDI avec Skype Entreprise Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)