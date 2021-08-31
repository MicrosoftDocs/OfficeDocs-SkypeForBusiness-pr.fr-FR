---
title: Composants et topologies pour le contrôle d’admission des appels dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planification du contrôle d’admission des appels (CAC) si vous avez un réseau MPLS, une ligne SIP ou une passerelle PSTN ou un PBX tiers. S’applique Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 6964d57af7f4b1218e502e1b7b8ffc6afee3f5d5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730903"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Composants et topologies pour le contrôle d’admission des appels dans Skype Entreprise

Planification du contrôle d’admission des appels (CAC) si vous avez un réseau MPLS, une ligne SIP ou une passerelle PSTN ou un PBX tiers. S’applique Skype Entreprise Server Voix Entreprise.

Les rubriques de cette section donnent des informations sur les considérations spécifiques de déploiement du contrôle d’admission des appels (CAC) avec différents types de topologies réseau.

## <a name="call-admission-control-on-an-mpls-network"></a>Contrôle d’admission des appels sur un réseau MPLS

Dans un réseau MPLS (Multiprotocol Label Switching), tous les sites sont connectés par un maillage. C’est-à-dire que tous les sites sont connectés directement au segment principal MPLS du fournisseur de services Internet, chaque site recevant la bande passante à utiliser sur une liaison WAN au cloud MPLS. Il n’y a aucun concentrateur réseau ou site central pour contrôler le routage IP. La figure suivante montre un réseau simple basé sur la technologie MPLS.

**Exemple de réseau MPLS**

![Cac avec MPLS.](../../media/CAC_MPLS_1.jpg)

Pour déployer le contrôle d’admission des appels dans un réseau MPLS, vous devez créer une région sur le réseau pour représenter le cloud MPLS et créer un site réseau pour représenter chaque site satellite MPLS. La figure suivante montre comment la région et les sites du réseau doivent être configurés pour représenter le réseau MPLS exemple dans la figure précédente. Les limites globales de bande passante et de session de bande passante sont ensuite basées sur la capacité de la liaison WAN de chaque site vers la région qui représente le cloud MPLS.

**Région et sites d’un réseau MPLS**

![Contrôle d’admission des appels (CAC) avec diagramme MPLS.](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>Contrôle d’admission des appels sur une trunk SIP

Pour déployer le contrôle d’admission des appels sur une jonction SIP, vous créez un site réseau pour représenter le fournisseur de services de téléphonie Internet (ITSP). Pour appliquer la stratégie de bande passante sur la jonction SIP, vous créez une stratégie intersite entre le site réseau dans votre entreprise et le site réseau créé pour représenter le fournisseur de services de téléphonie Internet.

La figure suivante montre un exemple de déploiement du contrôle d’admission des appels sur une jonction SIP.

**Configuration du contrôle d’admission des appels sur une jonction SIP**

![Diagramme de la trunking SIP du contrôle d’admission des appels.](../../media/CAC_SIP_trunk_1.jpg)

Pour configurer le contrôle d’admission des appels sur une jonction SIP, vous devrez exécuter les tâches suivantes pendant le déploiement du contrôle d’admission des appels :

1. Créez un site réseau pour représenter le fournisseur de services de téléphonie Internet. Associez le site réseau à une région réseau appropriée, et allouez une bande passante nulle pour l’audio et la vidéo pour ce site réseau. Pour plus d’informations, voir [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) dans la documentation de déploiement.

    > [!NOTE]
    > Pour le fournisseur de services de téléphonie Internet, cette configuration de site réseau n’est pas fonctionnelle. Les valeurs de stratégie de bande passante sont en fait appliquées à l’étape 2.

2. Créez un lien intersite pour la jonction SIP à l’aide des valeurs de paramètre pertinentes pour le site créé à l’étape 1. Par exemple, utilisez le nom du site réseau dans votre entreprise comme valeur du paramètre NetworkSiteID1 et le site réseau du fournisseur de services de téléphonie Internet comme valeur du paramètre NetworkSiteID2. Pour plus d’informations, voir [Create network intersite policies in Skype Entreprise Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).

3. Obtenez l’adresse IP du point de terminaison multimédia du contrôleur de frontière de session (SCB) auprès de votre itsp. Ajoutez cette adresse IP avec un masque de sous-réseau de 32 au site réseau qui représente le fournisseur de services de téléphonie Internet. Pour plus d’informations, voir [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Contrôle d’admission des appels avec une passerelle PSTN ou un PBX tiers

Cette rubrique décrit des exemples de déploiement du contrôle d’admission des appels (CAC) sur la liaison entre l’interface de passerelle du serveur de médiation et une passerelle PSTN (réseau téléphonique commuté) tierce ou pbX (private branch exchange).

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Cas 1 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et une passerelle PSTN

Le service Cac peut être déployé sur la liaison de réseau wan à partir de l’interface de passerelle du serveur de médiation vers une passerelle PBX ou PSTN tierce.

**Cas 1 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et une passerelle PSTN**

![Cas 1 : contrôle d’accès au contrôle d’accès entre la passerelle PSTN du serveur de médiation.](../../media/CAC_gateways_1.jpg)

Dans cet exemple, le service Cac est appliqué entre le serveur de médiation et une passerelle PSTN. Si un Skype Entreprise client sur le site réseau 1 passe un appel PSTN via la passerelle PSTN dans le site réseau 2, le média passe par la liaison wan. Par conséquent, deux vérifications cac sont effectuées pour chaque session PSTN :

- Entre l’application Skype Entreprise client et le serveur de médiation

- Entre le serveur de médiation et la passerelle PSTN

Cela fonctionne à la fois pour les appels PSTN entrants vers un client dans le site réseau 1 et pour les appels PSTN sortants provenant d’une application cliente dans Le site réseau 1.

> [!NOTE]
> Assurez-vous que le sous-réseau IP à qui appartient la passerelle PSTN est configuré et associé au site réseau 2.

> [!NOTE]
> Assurez-vous que le sous-réseau IP à qui appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.

> [!NOTE]
> Pour plus d’informations, voir [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Cas 2 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers avec point de terminaison multimédia

Cette configuration est similaire au cas 1. Dans les deux cas, le serveur de médiation connaît le périphérique qui arrête le média à l’extrémité opposée de la liaison wan et l’adresse IP de la passerelle PSTN ou du PBX avec point de terminaison multimédia (MTP) est configurée sur le serveur de médiation comme saut suivant.

**Cas 2 : CONTRÔLE D’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers avec MTP**

![Cas 2 : Contrôle d’accès au contrôle d’accès entre pbX du serveur de médiation avec MTP.](../../media/CAC_gateways_2.jpg)

Dans cet exemple, le service Cac est appliqué entre le serveur de médiation et le PBX/MTP. Si un Skype Entreprise client sur le site réseau 1 passe un appel PSTN via le PBX/MTP situé dans le site réseau 2, le média passe par la liaison wan. Par conséquent, pour chaque session PSTN, deux contrôles d’intégrité du contrôle d’intégrité sont effectués :

- Entre l’application Skype Entreprise client et le serveur de médiation

- Entre le serveur de médiation et le PBX/MTP

Cela fonctionne pour les appels PSTN entrants vers un client du site réseau 1 et les appels PSTN sortants provenant d’un client du Site réseau 1.

> [!NOTE]
> Assurez-vous que le sous-réseau IP à qui appartient le MTP est configuré et associé au site réseau 2.

> [!NOTE]
> Assurez-vous que le sous-réseau IP à qui appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.

> [!NOTE]
> Pour plus d’informations, voir [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Cas 3 : Contrôle d’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers sans point de terminaison multimédia

Le cas 3 est légèrement différent des deux premiers cas. S’il n’existe aucun MTP sur le PBX tiers, pour une demande de session sortante au PBX tiers, le serveur de médiation ne sait pas où le média s’interrompra dans la limite du PBX. Dans ce cas, le média circule directement entre le serveur de médiation et le périphérique de point de terminaison tiers.

**Cas 3 : CONTRÔLE D’accès au contrôle d’accès entre le serveur de médiation et un PBX tiers sans MTP**

![Cas 3 : CAC entre le PBX du serveur de médiation sans MTP.](../../media/CAC_gateways_3.jpg)

Dans cet exemple, si un utilisateur client Skype Entreprise sur le site réseau 1 appelle un utilisateur via le PBX, le serveur de médiation peut effectuer des vérifications cac uniquement sur la partie proxy (entre l’application cliente Skype Entreprise et le serveur de médiation). Étant donné que le serveur de médiation ne comprend pas d’informations sur le périphérique de point de terminaison pendant la demande de session, les vérifications du contrôle d’accès au contrôle d’accès ne peuvent pas être effectuées sur la liaison wan (entre le serveur de médiation et le point de terminaison tiers) avant l’établissement de l’appel. Cependant, une fois la session établie, le serveur de médiation facilite la gestion de la bande passante utilisée sur la connexion.

Pour les appels qui proviennent du point de terminaison tiers, les informations sur ce périphérique de point de terminaison sont disponibles au moment de la demande de session et la vérification cac peut être effectuée sur les deux côtés du serveur de médiation.

> [!NOTE]
> Assurez-vous que le sous-réseau IP à qui appartiennent les appareils de point de terminaison est configuré et associé au site réseau 2.

> [!NOTE]
> Assurez-vous que le sous-réseau IP à qui appartiennent les deux interfaces du serveur de médiation est configuré et associé au site réseau 1.

> [!NOTE]
> Pour plus d’informations, voir [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).