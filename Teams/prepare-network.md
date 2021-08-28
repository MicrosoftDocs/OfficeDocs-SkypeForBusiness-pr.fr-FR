---
title: Préparer le réseau de votre organisation pour Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: En savoir plus sur la préparation du réseau de votre organisation pour Microsoft Teams (exigences réseau, optimisation du réseau, besoins en matière de bande passante, etc.).
ms.localizationpriority: high
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
ms.openlocfilehash: 13bc12d5df1139bc76afa48751e7a7cb3c6197c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621966"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Préparer le réseau de votre organisation pour Microsoft Teams 

## <a name="network-requirements"></a>Configuration réseau requise

Si vous avez déjà [optimisé votre réseau pour Microsoft 365 ou Office 365](/Office365/Enterprise/assessing-network-connectivity), vous êtes probablement prêt pour Microsoft Teams. Dans tous les cas, et surtout si vous déployez rapidement Teams en tant que première charge de travail Microsoft 365 ou Office 365 pour prendre en charge les **employés distants**, vérifiez les étapes suivantes avant de commencer le déploiement de Teams :

1.  Est-ce que tous vos emplacements ont un accès à Internet (pour pouvoir se connecter à Microsoft 365 ou à Office 365) ? En plus du trafic web normal, assurez-vous d’avoir ouvert les ports TCP et les adresses IP répertoriés pour Teams dans [URL Office 365 et les plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

    > [!IMPORTANT]
    > Si vous devez vous fédérer avec Skype pour les entreprises, sur site ou en ligne, vous devrez configurer un enregistrement DNS supplémentaire.
    >
    >|Enregistrement DNS  |Service  |Protocol (Protocole)  |Priority (Priorité)  |Weight (Poids)  |Port  |Target (Cible)  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|SRV     |sipfederationtls     |TCP     |100     |1     |5061     |sipfed.online.lync.com     |
    
2.  Avez-vous un domaine vérifié pour Microsoft 365 ou Office 365 (par exemple, contoso.com) ?
    
    - Si votre organisation n’a pas déployé Microsoft 365 ou Office 365, consultez la [prise en main](/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, consultez là [FAQ sur les domaines](/microsoft-365/admin/setup/domains-faq).

3.  Votre organisation a-t-elle déployé Exchange Online et SharePoint Online ?
    
    - Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Comprendre l’interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md).
    - Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Comprendre l’interaction entre SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md).

Une fois que vous avez vérifié que vous répondez à ces exigences réseau, vous êtes prêt à [déployer Teams](./deploy-overview.md). Si vous êtes une grande entreprise multinationale ou si vous savez que vous avez des limites réseau, lisez la suite pour découvrir comment évaluer et optimiser votre réseau pour Teams.

> [!IMPORTANT]
> **Pour les établissements d’enseignement** : si votre organisation est un établissement d’enseignement et que vous utilisez un système d’information sur les élèves (SIE), [déployez la synchronisation des données scolaires](/schooldatasync/) avant de déployer Teams.
>  
> **Exécution de Skype Entreprise Server** en local : si votre organisation exécute Skype Entreprise Server en local (ou Lync Server), vous devez [configurer Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) pour synchroniser votre annuaire local avec Microsoft 365 ou Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Recommandation : surveillez votre réseau à l’aide du tableau de bord de qualité des appels et de l’analyse des appels 

Utilisez le [tableau de bord de la qualité des appels (TBQA)](turning-on-and-using-call-quality-dashboard.md) pour mieux connaître la qualité des appels et réunions dans Teams. Le TBQA peut vous aider à optimiser votre réseau en gardant un œil sur la qualité, la fiabilité et l’expérience utilisateur. Le TBQA examine la télémétrie d’agrégation pour l’ensemble d’une organisation où des modèles globaux peuvent apparaître, ce qui vous permet d’identifier les problèmes et de planifier la correction. De plus, le TBQA propose des rapports métriques enrichis qui fournissent des informations sur la qualité globale, sur la fiabilité et sur l’expérience utilisateur. 

Vous utiliserez [l’analyse des appels](set-up-call-analytics.md) pour évaluer les problèmes liés aux appels et aux réunions pour un utilisateur particulier.

## <a name="network-optimization"></a>Optimisation réseau

Les tâches suivantes sont facultatives et ne sont pas requises pour déployer Teams, en particulier si vous êtes une petite entreprise et que vous avez déjà déployé Microsoft 365 ou Office 365. Utilisez ces instructions pour optimiser les performances de votre réseau et de Teams, ou si vous savez que vous avez certaines limitations de réseau.

Vous pouvez avoir besoin d’optimiser davantage le réseau si :

  - Teams fonctionnent lentement (votre bande passante est peut-être insuffisante)
  - Les appels sont en continue (peut être dû à un pare-feu ou à des bloqueurs de proxy)
  - Les appels sont statiques et saccadés, ou la voix est robotique (peut être dû à une gigue ou une perte de paquets)

Pour une discussion détaillée sur l’optimisation du réseau, ainsi que des instructions sur l’identification et la résolution des problèmes de réseau, lisez les [principes de connectivité réseau de Microsoft 365 et Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).

<table>
<thead>
<tr class="header">
<th>Tâche d'optimisation du réseau</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planificateur de réseau</td>
<td><p>Pour obtenir de l’aide sur l’évaluation de votre réseau, notamment les calculs de bande passante et les exigences réseau au sein des emplacements physiques de votre organisation, consultez l’outil <a href="/microsoftteams/network-planner">Planificateur réseau</a> dans le <a href="https://admin.teams.microsoft.com">centre d’administration Teams</a>. Lorsque vous indiquez les détails de votre réseau et de votre utilisation de Teams, le planificateur de réseau calcule les exigences réseau requises pour le déploiement de Teams et de Voix Cloud dans les emplacements physiques de votre organisation.</p>
<p>Pour voir un exemple de scénario, consultez <a href="/microsoftteams/tutorial-network-planner-example">Utilisation du planificateur réseau : exemple de scénario</a>.</p></td>
</tr>
<tr class="even">
<td>Conseiller pour Teams</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Conseiller pour Teams</a> fait partie intégrante du <a href="https://admin.teams.microsoft.com">Centre d’administration Teams</a>. Il évalue votre environnement Microsoft 365 ou Office 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams.</td>
</tr>
<tr class="odd">
<td>Résolution des noms externes</td>
<td>Assurez-vous que tous les ordinateurs exécutant le client Teams peuvent résoudre des requêtes DNS externes pour découvrir les services fournis par Microsoft 365 ou Office 365 et que vos pare-feu n’empêchent pas l’accès. Pour plus d’informations sur la configuration des ports de pare-feu, consultez <a href="/microsoftteams/office-365-urls-ip-address-ranges">URL et plages d’adresses IP Microsoft 365 et Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Tenir à jour les sessions</td>
<td>Assurez-vous que votre pare-feu ne modifie pas les traductions d’adresses réseau (NAT) mappées ou les ports pour UDP.</td>
</tr><tr class="odd">
<td>Valider la taille du pool NAT</td>
<td>Validez la taille du pool traduction d’adresses réseau (NAT) requise pour la connectivité des utilisateurs. Lorsque plusieurs utilisateurs et appareils accèdent à Microsoft 365 ou Office 365 à l’aide de la <a href="/office365/enterprise/nat-support-with-office-365">traduction d’adresses réseau (NAT) ou de la traduction d’adresses de port (PAT)</a>, vous devez vous assurer que les appareils cachés derrière chaque adresse IP routable publiquement ne dépassent pas le nombre pris en charge. Assurez-vous que des adresses IP publiques adéquates sont affectées aux pools NAT afin d’éviter une insuffisance de ports. L’insuffisance de ports contribue à l’incapacité des utilisateurs et appareils internes à se connecter au service Microsoft 365 ou Office 365.</td>
</tr>
<tr class="even">
<td>Routage vers des centres de données Microsoft</td>
<td><a href="/office365/enterprise/client-connectivity">Implémenter le routage le plus efficace vers les centres de données Microsoft</a>. Identifiez les emplacements qui peuvent utiliser les points de sortie locaux ou régionaux pour vous connecter au réseau Microsoft le plus efficacement possible.</td>
</tr>
<tr class="odd">
<td>Guide sur la détection et la prévention des intrusions</td>
<td>Si votre environnement possède un système de <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">détection d’intrusions</a> ou un système de prévention (IDS ou IPS) déployé pour disposer d’une sécurité supplémentaire pour les connexions sortantes, n’oubliez pas d’autoriser toutes les URL Microsoft 365 ou Office 365.</td>
</tr>
<tr class="even">
<td>Configurer un VPN en tunnel segmenté</td>
<td><p>Nous vous recommandons de fournir un autre chemin d’accès pour le trafic Teams qui contourne le réseau privé virtuel (VPN), communément appelé <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN en tunnel segmenté</a>. Grâce au tunnel segmenté, le trafic pour Microsoft 365 ou Office 365 ne passe pas par le VPN, mais va directement vers Microsoft 365 ou Office 365. Contourner le VPN a un impact positif sur la qualité de Teams et réduit la charge à partir des appareils VPN et du réseau de l’organisation. Pour mettre en place un tunnel segmenté, consultez votre fournisseur VPN.</p>
<p>Nous vous recommandons de contourner le VPN pour les autres raisons suivantes :
<ul>
<li><p>Les VPN ne sont généralement pas conçus ou configurés pour prendre en charge les médias en temps réel.</p></li> 
<li><p>Certains VPN peuvent également ne pas prendre en charge les UDP (obligatoires pour Teams).</p></li> 
<li><p>Les VPN offrent également une phase supplémentaire de chiffrement au-dessus du trafic multimédia déjà chiffré.</p></li> 
<li><p>La connectivité à Teams peut ne pas être efficace en raison de l’épinglage de bande passante via un appareil VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Mettre en œuvre la qualité de service (QoS)</td>
<td><a href="/microsoftteams/qos-in-teams">Utilisez la qualité de service (QoS)</a> pour définir la priorité des paquets. La qualité des appels dans Teams est améliorée et vous aide à surveiller la qualité des appels et à les résoudre. QoS doit être implémenté sur tous les segments d’un réseau géré. Même lorsqu’un réseau a été adéquatement mis en service pour la bande passante, QoS fournit une atténuation des risques en cas d’événements réseau inattendus. Avec QoS, le trafic vocal est hiérarchisé de sorte que ces événements inattendus n’affectent pas la qualité.</td>
</tr>
<tr class="even">
<td>Optimisation du Wi-Fi</td>
<td><p>Tout comme un réseau VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel. La planification ou l’optimisation d’un réseau Wi-Fi pour prendre en charge Teams est un élément essentiel à prendre en considération pour un déploiement de haute qualité. Tenez compte de ces facteurs :</p>
<ul>
<li><p>Implémentez QoS ou WMM (Wi-Fi Multimedia) pour vous assurer que le trafic multimédia est hiérarchisé de façon appropriée sur vos réseaux Wi-Fi.</p></li>
<li><p>Planifiez et optimisez les bandes Wi-Fi et l’emplacement des points d’accès. La gamme de 2,4 GHz peut fournir une expérience adéquate en fonction de l'emplacement des points d'accès, mais les points d'accès sont souvent affectés par d'autres appareils grand public qui fonctionnent dans cette gamme. La gamme de 5 GHz est assez vaste et convient mieux aux éléments multimédias en temps réel, mais nécessite davantage de points d’accès pour obtenir une couverture suffisante. Les points de terminaison doivent également prendre en charge cette bande et être configurés pour l’exploiter en conséquence.</p></li>
<li><p>Si vous utilisez des réseaux WiFi à deux bandes, vous pouvez implémenter la direction de bandes. La <em>direction de bande</em> est une technique implémentée par les fournisseurs Wi-Fi pour inciter les clients à bandes doubles afin d’utiliser la gamme de 5 GHz.</p></li>
<li><p>Lorsque les points d’accès d’un même canal sont trop proches les uns des autres, ils peuvent provoquer un chevauchement des signaux et une concurrence involontaire, ce qui peut nuire à l’expérience de l’utilisateur. Veillez à ce que les points d'accès voisins se trouvent sur des canaux qui ne se superposent pas.</p></li>
</ul>
<p>Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil. Consultez votre fournisseur Wi-Fi pour obtenir des instructions spécifiques.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Configuration de bande passante requise

Teams est conçu pour offrir la meilleure expérience audio, vidéo et de partage de contenu, quelles que soient vos conditions réseau. Cependant, lorsque la bande passante est insuffisante, Teams privilégie la qualité audio par rapport à la qualité vidéo.

Lorsque la bande passante n’est pas limitée, Teams optimise la qualité multimédia, y compris l’audio haute fidélité, la résolution vidéo jusqu’à 1 080p et jusqu’à 30 images (images par seconde) pour la vidéo et le contenu.

Le tableau suivant décrit la manière dont Teams utilise la bande passante. Teams fait toujours preuve de prudence quant à l’utilisation de la bande passante et est en mesure de fournir une qualité vidéo HD en moins de 1,5 Mbits/s. La consommation réelle de bande passante pour chaque appel ou réunion audio/vidéo varie en fonction de plusieurs facteurs, tels que la disposition vidéo, la résolution vidéo et les images vidéo par seconde. Lorsque la bande passante disponible est plus élevée, la qualité et l’utilisation s’améliorent pour offrir une expérience optimale.

:::row:::
   :::column span="":::
      **Modalité**
   :::column-end:::
   :::column span="3":::
      **Exigences en bande passante (vitesse de transmission en Ko/s vers le haut/bas)**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      **Minimum**
   :::column-end:::
   :::column span="":::
      **Recommandé**
   :::column-end:::
   :::column span="":::
      **Performances optimales**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Audio**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Un-à-un
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Réunions
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Video**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Un-à-un
   :::column-end:::
   :::column span="":::
        150/150
   :::column-end:::
   :::column span="":::
        1 500/1 500
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Réunions
   :::column-end:::
   :::column span="":::
        150/200
   :::column-end:::
   :::column span="":::
        2 500/4 000
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Partage d’écran**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Un-à-un
   :::column-end:::
   :::column span="":::
        200/200
   :::column-end:::
   :::column span="":::
        1 500/1 500
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Réunions
   :::column-end:::
   :::column span="":::
        250/250
   :::column-end:::
   :::column span="":::
        2 500/2 500
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Mode Ensemble**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Un-à-un
   :::column-end:::
   :::column span="":::
        N/A
   :::column-end:::
   :::column span="":::
        N/A
   :::column-end:::
   :::column span="":::
        N/A
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Réunions
   :::column-end:::
   :::column span="":::
        1 000/1 500
   :::column-end:::
   :::column span="":::
        1 500/2 500
   :::column-end:::
   :::column span="":::
        2 500/4 000
   :::column-end:::
:::row-end:::

**Les performances minimales**, **recommandées** et **optimales en matière** de bande passante sont basées sur l'utilisation par point de terminaison. En règle générale, il existe un point de terminaison par utilisateur, tel qu’un ordinateur ou un appareil mobile. Toutefois, si un utilisateur participe à une réunion Teams sur ** un ordinateur *et* un appareil mobile, deux points de terminaison sont associés à cet utilisateur.

- Les exigences **minimales** en matière de bande passante pour les appels vidéo sont d’une résolution maximale de 240 p, de fréquences d’images de contenu de partage d’écran adaptatives de 1 875 à 7,5fps et de vidéo en mode ensemble/grande galerie jusqu’à une résolution de 540 p.  

- Les exigences **recommandées** en matière de bande passante pour les appels vidéo sont jusqu’à 1 080p de résolution <sup>\*</sup>, les fréquences d’images de contenu de partage d’écran s’adaptent de 7,5 à 30fps, et la vidéo en mode ensemble/grande galerie jusqu’à 1 080p de résolution <sup>\*</sup>.  

- **Meilleures performances** Les conseils offrent une meilleure fidélité vidéo pour les réunions de plus grands participants, des environnements à perte élevée et un contenu de mouvement plus élevé avec des fréquences d’images de contenu de partage d’écran adaptatives de 15 à 30fps.

<sup>\*</sup>Attendez-vous à une qualité jusqu’à 1 080p, mais en fonction des conditions de votre réseau, la résolution et la qualité des vidéos seront optimisées en conséquence.  

## <a name="related-topics"></a>Voir aussi

[Principes de connectivité réseau de Microsoft 365 et Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Points de terminaison internationaux : Skype Entreprise Online et Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Serveurs proxy pour Teams](proxy-servers-for-skype-for-business-online.md)

[Médias dans Teams : pourquoi les réunions sont-elles simples ?](https://aka.ms/teams-media)

[Médias dans Teams : les flux multimédias en profondeur](https://aka.ms/teams-media-flows)

[Modèles d’identité et authentification dans Teams](identify-models-authentication.md)

[Comment déployer Teams](./deploy-overview.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
