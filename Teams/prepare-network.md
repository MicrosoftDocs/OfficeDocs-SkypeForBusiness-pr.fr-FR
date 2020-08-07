---
title: Préparer le réseau de votre organisation pour Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Apprenez-en davantage sur la préparation du réseau de votre organisation à Microsoft Teams, y compris les exigences réseau, l’optimisation du réseau et les exigences en matière de bande passante.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: d0ce589ef972639928e4c8696f3ed23146126086
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583887"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Préparer le réseau de votre organisation pour Microsoft Teams 

## <a name="network-requirements"></a>Conditions de réseau requises

Si vous avez déjà [optimisé votre réseau pour microsoft 365 ou Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), vous êtes probablement prêt pour Microsoft Teams. Dans tous les cas, et en particulier si vous déployez des équipes rapidement en tant que premier Microsoft 365 ou Workload 365 pour prendre en charge les **travailleurs distants** : consultez les rubriques suivantes avant de commencer le déploiement d’équipes :

1.  Tous vos emplacements disposent d’un accès à Internet (de sorte qu’ils puissent se connecter à Microsoft 365 ou Office 365) ? Au minimum, en plus du trafic Web normal, assurez-vous que vous avez ouvert la commande suivante, pour tous les emplacements, pour les médias dans teams :

    |  |  |
    |---------|---------|
    |Ports     |Ports UDP <strong>3478</strong> à <strong>3481</strong>        |
    |[Adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>et <strong>52.120.0.0/14</strong>         |

> [!IMPORTANT]
> Si vous avez besoin de fédérer avec Skype entreprise, en local ou en ligne, vous devrez configurer des enregistrements DNS supplémentaires.
>
>|Enregistrements CNAMe/nom d’hôte  |TTL  |Pointe vers l’adresse ou la valeur  |
>|---------|---------|---------|
>|SIP     |    3600     |    sipdir.online.lync.com     |
>|lyncdiscover     |   3600      |    webdir.online.lync.com     |
>


    
2.  Avez-vous un domaine vérifié pour Microsoft 365 ou Office 365 (par exemple, contoso.com) ?
    
      - Si votre organisation n’a pas déployé Microsoft 365 ou Office 365, voir [commencer](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).
      - Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, voir le [Forum aux questions sur les domaines](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).

3.  Votre organisation a-t-elle déployé Exchange Online et SharePoint Online ?
    
      - Si votre organisation n’a pas Exchange Online, voir [comprendre comment Exchange et Microsoft teams interagissent](exchange-teams-interact.md).
      - Si votre organisation ne dispose pas de SharePoint Online, voir [comprendre comment SharePoint Online et OneDrive entreprise interagissent avec Microsoft teams](sharepoint-onedrive-interact.md).

Une fois que vous avez vérifié que vous répondez à ces exigences réseau, vous pouvez être prêt à [déployer teams](How-to-roll-out-teams.md). S’il s’agit d’une grande entreprise multinationale, ou si vous savez que vous avez des limitations réseau, poursuivez votre lecture pour découvrir comment évaluer et optimiser votre réseau pour Teams.

> [!IMPORTANT]
> **Pour les établissements d’enseignement**: Si votre organisation est une institution éducative et que vous utilisez un système d’information sur les étudiants, [déployez School Data Sync](https://docs.microsoft.com/schooldatasync/) avant de déployer Teams.
>  
> **Exécution de Skype entreprise Server sur site**: Si votre organisation exécute Skype entreprise Server sur site (ou Lync Server), vous devez [configurer Azure ad Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) pour synchroniser votre annuaire local avec Microsoft 365 ou Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Meilleure pratique : surveiller votre réseau à l’aide de bord et d’appels d’analyse 

Utilisez le [tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md) pour mieux comprendre la qualité des appels et des réunions dans Teams. BORD vous permet d’optimiser votre réseau en effectuant un œil plus étroit sur la qualité, la fiabilité et l’interface utilisateur. BORD examine la télémétrie globale d’une entreprise dans laquelle les modèles globaux peuvent être évidents, ce qui vous permet d’identifier les problèmes et de planifier la correction. Par ailleurs, bord fournit des rapports métriques enrichis qui vous permettent d’avoir une vue d’ensemble de la qualité, de la fiabilité et de l’expérience utilisateur. 

L’analyse des [appels](set-up-call-analytics.md) vous permet d’identifier les problèmes liés aux appels et aux réunions d’un utilisateur individuel.

## <a name="network-optimization"></a>Optimisation du réseau

Les tâches suivantes sont facultatives et ne sont pas requises pour le déploiement d’équipes, en particulier si vous êtes une petite entreprise et que vous avez déjà déployé Microsoft 365 ou Office 365. Utilisez ces instructions pour optimiser les performances de votre réseau et de votre équipe, ou si vous savez que vous disposez de limitations réseau.

Vous souhaiterez peut-être procéder à une optimisation du réseau supplémentaire dans les cas suivants :

  - Teams est lent (il est possible que vous ayez une bande passante insuffisante)
  - Les appels sont interrompus (peut être dû au pare-feu ou aux bloqueurs de proxy)
  - Les appels sont statiques et découpés, ou les voix (par exemple, les robots peuvent être instables ou perdus en paquets)

Pour une description détaillée de l’optimisation du réseau, y compris des recommandations en matière d’identification et de résolution des problèmes de réseau, voir [principes de connexion réseau Microsoft 365 et Office 365](https://aka.ms/pnc).

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
<td><p>Pour obtenir de l’aide sur votre réseau, notamment les calculs de bande passante et les exigences réseau dans les emplacements physiques de votre organisation, consultez l’outil <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> , dans le <a href="https://admin.teams.microsoft.com">Centre d’administration teams</a>. Lorsque vous fournissez les informations relatives à votre réseau et à l’utilisation des équipes, le planificateur réseau calcule la configuration requise pour le déploiement d’équipes et de la voix Cloud dans les emplacements physiques de votre organisation.</p>
<p>Pour obtenir un exemple de scénario, voir <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">scénario d’utilisation du planificateur de réseaux</a>.</p></td>
</tr>
<tr class="even">
<td>Conseiller en équipe</td>
<td>Le <a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">conseiller d’équipe</a> est intégré au <a href="https://admin.teams.microsoft.com">Centre d’administration teams</a>. Il évalue votre environnement Microsoft 365 ou Office 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams.</td>
</tr>
<tr class="odd">
<td>Résolution de noms externes</td>
<td>Assurez-vous que tous les ordinateurs exécutant le client teams peuvent résoudre les requêtes DNS externes pour découvrir les services fournis par Microsoft 365 ou Office 365 et que vos pare-feu n’empêchent pas Access. Pour plus d’informations sur la configuration des ports de pare-feu, consultez les <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">URL et les plages d’adresses IP de Microsoft 365 et Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Conserver la persistance de session</td>
<td>Assurez-vous que votre pare-feu ne modifie pas les adresses ou ports de traduction d’adresses réseau (NAT) mappés pour UDP.</td>
</tr><tr class="odd">
<td>Valider la taille du pool NAT</td>
<td>Validez la taille du pool de traduction d’adresses réseau (NAT) requise pour la connectivité utilisateur. Lorsque plusieurs utilisateurs et appareils accèdent à Microsoft 365 ou Office 365 à l’aide de la <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">traduction d’adresses réseau (NAT) ou de la traduction d’adresses de port (Pat)</a>, vous devez vous assurer que les périphériques cachés derrière chaque adresse IP routable publique ne dépassent pas le numéro pris en charge. Assurez-vous que les adresses IP publiques appropriées sont affectées aux pools NAT pour empêcher les épuisements de port. L’épuisement du port contribuera aux utilisateurs internes et aux appareils qui ne peuvent pas se connecter au service Microsoft 365 ou Office 365.</td>
</tr>
<tr class="even">
<td>Routage vers les centres de données Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Appliquez le routage le plus efficace aux centres de données Microsoft</a>. Identifiez les emplacements qui peuvent utiliser des points de sortie locaux ou régionaux pour vous connecter au réseau Microsoft aussi efficacement que possible.</td>
</tr>
<tr class="odd">
<td>Recommandations en matière de détection d’intrusion et de prévention</td>
<td>Si votre environnement possède un système de <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">détection des intrusions</a> ou de prévention (IDS/IPS) déployé pour une couche supplémentaire de sécurité pour les connexions sortantes, veillez à autoriser toutes les url Microsoft 365 ou Office 365.</td>
</tr>
<tr class="even">
<td>Configurer une connexion VPN de tunneling fractionné</td>
<td><p>Nous vous recommandons de fournir un autre chemin pour le trafic d’équipes qui ignore le réseau privé virtuel (VPN), également connu sous le nom de [VPN de tunneling partagé](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing). Le tunneling fractionné signifie que le trafic pour Microsoft 365 ou Office 365 n’est pas transmis via le réseau privé virtuel mais qu’il accède directement à Microsoft 365 ou Office 365. Ignorer votre VPN aura un impact positif sur la qualité des équipes et réduit la charge des appareils VPN et du réseau de l’organisation. Pour implémenter une connexion VPN de tunneling fractionné, travaillez avec votre fournisseur de VPN.</p>
<p>Autres raisons pour lesquelles nous vous conseillons de contourner le VPN :
<ul>
<li><p>Les réseaux privés virtuels ne sont généralement pas conçus ou configurés pour prendre en charge les contenus multimédias en temps réel.</p></li> 
<li><p>Certains réseaux privés virtuels peuvent également ne pas prendre en charge le protocole UDP (obligatoire pour Teams).</p></li> 
<li><p>Les réseaux privés virtuels introduisent également une couche supplémentaire de chiffrement au-dessus du trafic multimédia déjà crypté.</p></li> 
<li><p>La connectivité à teams peut ne pas être efficace en raison d’un trafic d’épinglage par un appareil VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Mettre en œuvre la QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Utilisez la qualité de service (QoS)</a> pour configurer la hiérarchisation des paquets. La qualité des appels sera ainsi améliorée en équipe et vous pourrez surveiller et résoudre les problèmes de qualité des appels. La QoS doit être implémentée sur tous les segments d’un réseau géré. Même si un réseau a été configuré de manière appropriée pour la bande passante, la fonction QoS fournit une réduction des risques en cas d’événement réseau inattendus. Avec la qualité de service (QoS), le trafic vocal est prioritaire de sorte que ces événements inattendus n’affectent pas la qualité.</td>
</tr>
<tr class="even">
<td>Optimiser le WiFi</td>
<td><p>À l’instar des réseaux VPN, les réseaux WiFi ne sont pas nécessairement conçus ou configurés pour prendre en charge les contenus multimédias en temps réel. Pour un déploiement de grande qualité, la planification d’un réseau WiFi pour la prise en charge des équipes est une considération importante. Prenez en compte les facteurs suivants :</p>
<ul>
<li><p>Mettez en œuvre le contenu multimédia QoS ou WiFi (WMM) pour vous assurer que le trafic multimédia est prioritaire sur vos réseaux WiFi.</p></li>
<li><p>Planifiez et optimisez les bandes Wi-Fi et l’emplacement du point d’accès. La plage de 2,4 GHz peut offrir une connaissance appropriée en fonction du placement du point d’accès, mais les points d’accès sont souvent affectés par d’autres appareils grand public qui fonctionnent dans cette plage. La plage de 5 GHz est mieux adaptée aux éléments multimédias en temps réel en raison de sa gamme dense, mais elle nécessite davantage de points d’accès pour bénéficier d’une couverture suffisante. Les points de terminaison doivent également prendre en charge cette plage et être configurés pour exploiter ces bandes en conséquence.</p></li>
<li><p>Si vous utilisez des réseaux WiFi double bande, envisagez de mettre en place une direction à bandes. La <em>direction de bandes</em> est une technique mise en œuvre par les fournisseurs de réseaux Wi-Fi pour influer sur les clients à double bande et utiliser la plage de 5 GHz.</p></li>
<li><p>Lorsque les points d’accès du même canal sont trop proches, ils peuvent provoquer le chevauchement du signal et la concurrence involontaire, ce qui engendre une mauvaise utilisation de l’utilisateur. Assurez-vous que les points d’accès adjacents s’exécutent sur des canaux qui ne se chevauchent pas.</p></li>
</ul>
<p>Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Pour obtenir des instructions spécifiques, contactez votre revendeur WiFi.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Bande passante requise

Teams est conçu pour offrir la meilleure expérience de partage audio, vidéo et de contenu quelle que soit l’état de votre réseau. Cela dit, lorsque la bande passante est insuffisante, teams hiérarchise la qualité audio de la qualité vidéo.

Si la bande passante *n’est pas* limitée, teams optimise la qualité du média, avec une résolution vidéo de 1080 30 IPS pour la vidéo et l' 15fps pour le contenu et l’audio haute fidélité. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Rubriques connexes

[Principes de connectivité réseau de Microsoft 365 et Office 365](https://aka.ms/pnc)

[Points de terminaison internationaux : Skype entreprise Online et Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Serveurs proxy pour teams](proxy-servers-for-skype-for-business-online.md)

[Multimédia dans teams : pourquoi des réunions sont simples](https://aka.ms/teams-media)

[Multimédia dans teams : plongée en profondeur dans les flux multimédias](https://aka.ms/teams-media-flows)

[Modèles d’identité et authentification dans Teams](identify-models-authentication.md)

[Comment déployer Teams](How-to-roll-out-teams.md)

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
