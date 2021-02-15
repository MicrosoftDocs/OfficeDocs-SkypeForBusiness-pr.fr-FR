---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Découvrez comment préparer le réseau de votre organisation pour Microsoft Teams, notamment la exigences réseau, l’optimisation du réseau et les besoins en bande passante.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099571"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Préparer le réseau de votre organisation pour Microsoft Teams 

## <a name="network-requirements"></a>Conditions de réseau requises

Si vous avez déjà optimisé votre réseau pour [Microsoft 365 ou Office 365,](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)vous êtes probablement prêt pour Microsoft Teams. Dans tous les cas, et surtout si vous déploiementz Teams rapidement lors de votre première charge de travail Microsoft 365 ou Office 365 pour prendre en charge les travailleurs à **distance,** consultez ce qui suit avant de commencer votre déploiement de Teams :

1.  Tous vos emplacements ont-ils accès à Internet (de sorte qu’ils peuvent se connecter à Microsoft 365 ou Office 365) ? Au minimum, en plus du trafic web normal, assurez-vous d’avoir ouvert ce qui suit, pour tous les emplacements, pour les médias dans Teams :

    |  |  |
    |---------|---------|
    |Ports     |Ports UDP <strong>3478</strong> à <strong>3481</strong>        |
    |[Adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18,</strong> <strong>52.112.0.0/14</strong>et <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Si vous devez vous fédérer avec Skype Entreprise, en local ou en ligne, vous devrez configurer des enregistrements DNS supplémentaires.
    >
    >|CNAME Records / Host name (Enregistrements CNAME/Nom d’hôte)  |TTL (TTL)  |Pointe vers l’adresse ou la valeur  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Avez-vous un domaine vérifié pour Microsoft 365 ou Office 365 (par exemple, contoso.com) ?
    
    - Si votre organisation n’a pas déployé Microsoft 365 ou Office 365, voir [Commencer.](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)
    - Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, consultez le Forum aux [questions des domaines.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)

3.  Votre organisation a-t-elle déployé Exchange Online et SharePoint Online ?
    
    - Si votre organisation n’a pas Exchange Online, voir [Comprendre comment Exchange et Microsoft Teams interagissent.](exchange-teams-interact.md)
    - Si votre organisation n’a pas SharePoint Online, voir Comprendre comment SharePoint Online et [OneDrive Entreprise interagissent avec Microsoft Teams.](sharepoint-onedrive-interact.md)

Une fois que vous avez vérifié que vous avez satisfait à ces exigences réseau, vous êtes peut-être prêt [à déployer Teams.](How-to-roll-out-teams.md) Si vous êtes une grande multinationale ou si vous savez que vous avez des limites réseau, découvrez comment évaluer et optimiser votre réseau pour Teams.

> [!IMPORTANT]
> **Pour les établissements** d’enseignement : si votre organisation est un établissement d’enseignement et que vous utilisez un système de gestion des informations sur les étudiants, déployez [School Data Sync](https://docs.microsoft.com/schooldatasync/) avant de déployer Teams.
>  
> Exécution de Skype Entreprise **Server** local : si votre organisation exécute Skype Entreprise Server sur site (ou Lync Server), vous devez configurer [Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) pour synchroniser votre annuaire local avec Microsoft 365 ou Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Meilleure pratique : Surveiller votre réseau à l’aide du DQD et de l’analyse des appels 

Utilisez le [tableau de bord de](turning-on-and-using-call-quality-dashboard.md) qualité des appels pour obtenir des informations sur la qualité des appels et des réunions dans Teams. Le CQD peut vous aider à optimiser votre réseau en gardant un œil sur la qualité, la fiabilité et l’expérience utilisateur. Le DQD examine la télémétrie agrégée pour l’ensemble d’une organisation dans laquelle les modèles globaux peuvent s’identifier, ce qui vous permet d’identifier les problèmes et de planifier la correction. En outre, le CQD fournit des rapports métriques enrichis qui fournissent des informations sur la qualité, la fiabilité et l’expérience utilisateur globales. 

Vous utiliserez les données [d’analyse des appels](set-up-call-analytics.md) pour examiner les problèmes liés aux appels et aux réunions pour un utilisateur individuel.

## <a name="network-optimization"></a>Optimisation du réseau

Les tâches suivantes sont facultatives et ne sont pas nécessaires pour déployer Teams, en particulier si vous êtes une petite entreprise et que vous avez déjà déployé Microsoft 365 ou Office 365. Utilisez ces instructions pour optimiser les performances de votre réseau et de Teams ou si vous savez que vous avez certaines limitations réseau.

Vous souhaitez peut-être optimiser davantage votre réseau si :

  - Teams s’exécute lentement (vous avez peut-être une bande passante insuffisante)
  - Les appels continuent de se bloquer (ils peuvent être dus à un pare-feu ou à des bloqueurs de proxy)
  - Les appels sont statiques et cut out, ou les voix ressemblent à des robots (peut être une gigue ou une perte de paquets)

Pour une discussion approfondie de l’optimisation du réseau, y compris des conseils pour identifier et résoudre les problèmes de réseau, lisez Les principes de connectivité réseau de [Microsoft 365 et Office 365.](https://aka.ms/pnc)

<table>
<thead>
<tr class="header">
<th><strong>Tâche d’optimisation du réseau</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planificateur réseau</td>
<td><p>Pour obtenir de l’aide pour évaluer votre réseau, y compris les <a href="https://docs.microsoft.com/microsoftteams/network-planner"></a> calculs de bande passante et les exigences réseau dans les emplacements physiques de votre organisation, consultez l’outil Planificateur réseau dans le Centre d’administration <a href="https://admin.teams.microsoft.com">Teams.</a> Lorsque vous fournissez les détails de votre réseau et que vous fournissez l’utilisation de Teams, le Planificateur réseau calcule votre exigences réseau pour déployer Teams et voix cloud sur les emplacements physiques de votre organisation.</p>
<p>Pour consulter un exemple de scénario, voir <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Utiliser le Planificateur réseau - exemple de scénario.</a></p></td>
</tr>
<tr class="even">
<td>Conseiller pour Teams</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Conseiller pour Teams fait</a> partie du Centre <a href="https://admin.teams.microsoft.com">d’administration Teams.</a> Il évalue votre environnement Microsoft 365 ou Office 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams.</td>
</tr>
<tr class="odd">
<td>Résolution de noms externes</td>
<td>Assurez-vous que tous les ordinateurs exécutant le client Teams peuvent résoudre des requêtes DNS externes pour découvrir les services fournis par Microsoft 365 ou Office 365 et que vos pare-feu n’empêchent pas l’accès. Pour plus d’informations sur la configuration des ports du pare-feu, voir URL et <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">plages d’adresses IP Microsoft 365 et Office 365.</a></td>
</tr>
<tr class="odd">
<td>Maintenir la persistance des sessions</td>
<td>Assurez-vous que votre pare-feu ne modifie pas les adresses de traduction d’adresses réseau mappées (NAT) ou les ports pour UDP.</td>
</tr><tr class="odd">
<td>Valider la taille du pool NAT</td>
<td>Validez la taille de pool de traduction d’adresses réseau (NAT) requise pour la connectivité des utilisateurs. Lorsque plusieurs utilisateurs et appareils accèdent à Microsoft 365 ou Office 365 à l’aide de la traduction d’adresses réseau (NAT) ou de la traduction d’adresses de port <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">(PAT),</a>vous devez vous assurer que les appareils masqués derrière chaque adresse IP routable publiquement ne dépassent pas le nombre pris en charge. Assurez-vous que des adresses IP publiques correctes sont affectées aux pools de nats pour éviter l’épuisement du port. L’épuisement des ports contribue aux utilisateurs internes et aux appareils qui ne peuvent pas se connecter au service Microsoft 365 ou Office 365.</td>
</tr>
<tr class="even">
<td>Routage vers des centres de données Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implémenter le routage le plus efficace vers les centres de données Microsoft.</a> Identifiez les emplacements qui peuvent utiliser des points de sortie locaux ou régionaux pour se connecter au réseau Microsoft le plus efficacement possible.</td>
</tr>
<tr class="odd">
<td>Conseils sur la détection des intrusions et la prévention des intrusions</td>
<td>Si votre environnement dispose d’un système de détection ou de protection des <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">intrusions</a> (IDS/IPS) déployé pour une couche supplémentaire de sécurité pour les connexions sortantes, n’oubliez pas d’autoriser toutes les URL Microsoft 365 ou Office 365.</td>
</tr>
<tr class="even">
<td>Configurer un VPN avec tunnel fractioné</td>
<td><p>Nous vous recommandons de fournir un autre chemin pour le trafic teams qui ignore le réseau privé virtuel (VPN), communément appelé VPN avec <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">tunnel fractionné.</a> La tunnellation fractionnée signifie que le trafic pour Microsoft 365 ou Office 365 ne passe pas par le VPN, mais passe directement à Microsoft 365 ou Office 365. Ignorer votre VPN a un impact positif sur la qualité de Teams et réduit la charge provenant des appareils VPN et du réseau de l’organisation. Pour implémenter un VPN avec tunnel fractionnel, travaillez avec votre fournisseur VPN.</p>
<p>Autres raisons pour lesquelles nous recommandons d’ignorer le vpn :
<ul>
<li><p>Les réseauxvp n’ont généralement pas été conçus ou configurés pour prendre en charge les médias en temps réel.</p></li> 
<li><p>Certains VVP peuvent également ne pas prise en charge le UDP (requis pour Teams).</p></li> 
<li><p>Les réseauxvpns offrent également une couche supplémentaire de chiffrement sur le trafic de médias déjà chiffré.</p></li> 
<li><p>La connectivité à Teams peut ne pas être efficace en raison de l’épinglage de cheveux via un appareil VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Mettre en œuvre la QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Utilisez la qualité de service (QoS)</a> pour configurer la hiérérisation des paquets. Cela permettra d’améliorer la qualité des appels dans Teams et de vous aider à surveiller et à résoudre les problèmes de qualité de l’appel. La QoS doit être implémentée sur tous les segments d’un réseau géré. Même lorsqu’un réseau a été correctement mis en service pour la bande passante, la qualité de service fournit un atténuation des risques en cas d’événements réseau inattendus. Avec la QoS, le trafic vocal est hiérarchisé afin que ces événements inattendus n’affectent pas la qualité de façon négative.</td>
</tr>
<tr class="even">
<td>Optimiser le WiFi</td>
<td><p>Tout comme les réseaux VPN, les réseaux WiFi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. La planification ou l’optimisation d’un réseau WiFi pour prendre en charge Teams est une considération importante pour un déploiement de haute qualité. Prenons les facteurs suivants :</p>
<ul>
<li><p>Implémentez QoS ou WiFi Multimedia (WMM) pour vous assurer que le trafic de médias est correctement hiérarchisé sur vos réseaux WiFi.</p></li>
<li><p>Planifiez et optimisez les bandes Wifi et le placement des points d’accès. La plage de 2,4 GHz peut fournir une expérience appropriée en fonction du placement des points d’accès, mais les points d’accès sont souvent affectés par d’autres appareils grand public qui fonctionnent dans cette plage. La plage de 5 GHz est mieux adaptée aux médias en temps réel en raison de sa plage étendue, mais nécessite davantage de points d’accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.</p></li>
<li><p>Si vous utilisez des réseaux WiFi à double bande, envisagez d’implémenter le directeur de bande. <em>La musique band</em> est une technique implémentée par des fournisseurs WiFi pour influencer les clients à double bande pour utiliser la plage à 5 GHz.</p></li>
<li><p>Lorsque les points d’accès du même canal sont trop proches les uns des autres, ils peuvent entraîner le chevauchement des signaux et la concurrence involontaire, ce qui peut entraîner une mauvaise expérience pour l’utilisateur. Assurez-vous que les points d’accès l’un à côté des autres se superposent sur des canaux qui ne se chevauchent pas.</p></li>
</ul>
<p>Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Pour obtenir des conseils spécifiques, consultez votre fournisseur WiFi.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Bande passante requise

Teams est conçu pour offrir la meilleure expérience audio, vidéo et de partage de contenu quelles que soient vos conditions réseau. Cela dit, lorsque la bande passante est insuffisante, Teams privilégie la qualité audio à la qualité vidéo.

Lorsque la bande passante *n’est* pas limitée, Teams optimise la qualité multimédia, y compris la résolution vidéo de 1 080p, jusqu’à 30fps pour la vidéo et 15fps pour le contenu, ainsi que l’audio haute fidélité. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Rubriques connexes

[Principes de connectivité réseau de Microsoft 365 et Office 365](https://aka.ms/pnc)

[Points de terminaison internationaux : Skype Entreprise Online et Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Serveurs proxy pour Teams](proxy-servers-for-skype-for-business-online.md)

[Média dans Teams : Pourquoi les réunions sont simples](https://aka.ms/teams-media)

[Média dans Teams : plonger en profondeur dans les flux multimédias](https://aka.ms/teams-media-flows)

[Modèles d’identité et authentification dans Teams](identify-models-authentication.md)

[Comment déployer Teams](How-to-roll-out-teams.md)

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
