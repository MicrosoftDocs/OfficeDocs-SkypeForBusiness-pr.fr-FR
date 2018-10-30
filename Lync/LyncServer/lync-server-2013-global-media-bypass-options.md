---
title: Options globales du contournement de média dans Lync Server 2013
TOCTitle: Options globales du contournement de média dans Lync Server 2013
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398255(v=OCS.15)
ms:contentKeyID: 49296415
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Options globales du contournement de média dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

> [!NOTE]  
> Cette rubrique suppose que vous avez déjà configuré le contournement de média pour des jonctions vers un homologue (une passerelle de réseau téléphonique commuté (PSTN, Public Switched Telephone Network), un PBX IP ou un contrôleur SBC chez un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le média contourne toujours le serveur de médiation.

En plus d’activer le contournement de média pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres globaux du contournement de média. Les paramètres globaux du contournement de média peuvent spécifier de toujours tenter le contournement de média pour les appels vers le PSTN ou de l’employer en utilisant le mappage des sous-réseaux vers les sites et les régions réseau, ce qui est similaire à ce que fait le contrôle d’admission des appels, une autre fonctionnalité vocale avancée. Lorsque le contournement de média et le contrôle d’admission des appels sont tous les deux activés, les informations relatives aux régions, aux sites et aux sous-réseaux qui sont spécifiées pour le contrôle d’admission des appels sont automatiquement utilisées pour déterminer si le contournement de média doit être employé. Cela signifie que vous ne pouvez pas spécifier de toujours tenter le contournement de média pour les appels vers le réseau commuté public (PSTN) lorsque le contrôle d’admission des appels est activé.

Cette rubrique décrit comment utiliser le Panneau de configuration Lync Server et Lync Server Management Shell ensemble pour configurer les paramètres globaux du contournement de média.

> [!NOTE]  
> Pour configurer le contournement de média en suivant cette procédure, la connectivité entre les clients et l’homologue du serveur de médiation (par exemple, une passerelle PSTN, un PBX IP ou un contrôleur SBC d’un fournisseur de jonction SIP) doit être de bonne qualité. Si des restrictions de bande passante sont appliquées sur la liaison, le contournement de média ne peut pas être appliqué aux appels. Le contournement de média ne va pas interagir avec chaque passerelle PSTN, chaque système IP-PBX et chaque SBC. Microsoft a testé un ensemble de passerelles PSTN et des SBC avec des partenaires certifiés et a effectué des tests avec des systèmes IP-PBX de Cisco. Le contournement de média est uniquement pris en charge avec les produits et versions répertoriés dans « Infrastructure qualifiée pour Microsoft Lync » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x40C</a>

## Étapes suivantes : choisir les paramètres globaux du contournement de média

Après avoir activé le contournement de média sur des connexions de jonction vers un homologue pour des sites ou des services spécifiques, utilisez le contenu suivant pour :

  - Activer toujours le contournement de média, comme il est indiqué dans [Configurer le contournement de média dans Lync Server 2013 pour toujours contourner le serveur de médiation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - Ou, configurer le contournement de média pour utiliser les informations relatives aux sites et aux régions, comme il est indiqué dans [Configurer les paramètres globaux du contournement de média dans Lync Server 2013 pour utiliser les informations relatives aux sites et aux régions](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

## Voir aussi

#### Tâches

[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  

#### Concepts

[Configuration de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

