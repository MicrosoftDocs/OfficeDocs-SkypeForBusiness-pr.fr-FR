---
title: Étude de cas Teams voix Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786026"
---
# <a name="contoso-case-study-phone-system"></a>Étude de cas Contoso : Phone System

En fonction de l’emplacement géographique et d’autres facteurs, les bureaux de Contoso ont été bureaux à l’aide des solutions téléphoniques suivantes :

- Type de site A : skype entreprise Voix Entreprise

- Type de site B : systèmes de téléphonie hérités traditionnels

- Type de site C : combinaison de systèmes téléphoniques Skype Voix Entreprise et des systèmes de téléphonie hérités traditionnels


Pour implémenter une solution Microsoft Phone System pour l’ensemble de l’organisation, Contoso devait déterminer pour chaque type de site les options suivantes qui seraient utilisées avec le système téléphonique public commuté pour se connecter au réseau téléphonique commuté &mdash; &mdash; (PSTN) :

- Système téléphonique avec forfait d’appels 

- Système téléphonique avec son propre opérateur PSTN via un routage direct 

- Combinaison du système téléphonique avec le plan d’appels et le système téléphonique avec un opérateur PSTN qui lui est propre via un routage direct
 
Pour déterminer la solution appropriée pour leur organisation, Contoso a utilisé les solutions téléphoniques Microsoft et les [appels](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) de session Ignite 2019 dans [Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Type de site A : skype entreprise Voix Entreprise 

La Voix Entreprise Skype Entreprise contoso a été définie comme hub et s’est exprimé. Il y avait un emplacement central qui maincait la passerelle PSTN dans la région qui fournissait la connexion au réseau PSTN pour les utilisateurs de Skype Entreprise Voix Entreprise dans le pays. Bien souvent, ces sites satellitaires ne possèdent pas leur propre sortie Internet. Les numéros pour ces utilisateurs résident sur la ligne SIP qui se connecte à un SBC existant. 

Pour déterminer si le SBC déjà déployé est certifié pour le routage direct et la dérivation média, Contoso a coché la liste des contrôleurs de session certifiés pour le [routage direct.](direct-routing-border-controllers.md)  

Les habitudes de numérotation de l’utilisateur étaient de composer un utilisateur sur l’ancien système téléphonique à l’aide d’une extension, même si l’utilisateur dispose d’un client Skype Entreprise disponible pour l’audio P2T. 

Contoso a basé sa décision sur les questions suivantes :

- Q. Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?<br>
  A. Non 

- Q. Devons-nous interopérables avec des systèmes PBX tiers et d’autres équipements téléphoniques ?<br>
  A. Non 

- Q. Devons-nous conserver notre opérateur tiers actuel ?<br> A. Oui (pays régulés) et Non 

- Q. Devons-nous obtenir le retour sur investissement sur des SBCs déployés ?<br> A. Oui et Non  

- Q. Les plans d’appel PSTN Microsoft sont-ils disponibles dans cette région ?<br> A. Oui et Non 

En se basant sur les réponses à leurs questions, Contoso a décidé de :

- Déplacez les utilisateurs situés dans une région dans laquelle des plans d’appel PSTN sont disponibles vers Phone System avec des forfaits d’appels. 

- Déplacer les utilisateurs situés dans une région où des plans d’appel RTC sont disponibles, les utilisateurs situés sur un site où le retour sur investissement sur les SBCs n’ont pas encore été satisfaits et les utilisateurs résidant dans un pays qui dispose d’une réglementation téléphonique vers un système téléphonique avec un routage direct. 

Le diagramme suivant illustre le déploiement initial de Skype Voix Entreprise entreprise et la façon dont ce déploiement a été migré vers les plans d’appels Microsoft et le routage direct :

![Diagramme montrant des états avant et après](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Type de site B : systèmes de téléphonie hérités traditionnels

Contoso avait de nombreux bureaux qui tirent parti de systèmes de téléphonie hérités. Un sous-ensemble d’utilisateurs avait un numéro de téléphone E1.64, tandis que d’autres n’avaient qu’une extension. Ces numéros résident sur la ligne TDM de la passerelle PSTN. La numérotation intras site a été configurée en tirant parti d’un code de site devant l’extension pour déterminer l’emplacement d’itinéraire de l’appel. Les habitudes de numérotation des utilisateurs deaient composer le numéro par poste.   

Contoso a basé sa décision sur les questions suivantes :

- Q. Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?<br>
  A. Non 

- Q. Devons-nous interopérables avec des systèmes PBX tiers et d’autres équipements téléphoniques ?<br> A. Oui

- Q. Devons-nous conserver notre opérateur tiers actuel ?<br> A. Non 

- Q. L’offre d’appels PSTN de Microsoft est-elle disponible dans notre région ?<br> A. Oui et Non 

En se basant sur les réponses à leurs questions, Contoso a décidé de : 

- Déplacez les utilisateurs situés dans une région dans laquelle des plans d’appel PSTN sont disponibles vers Phone System avec des forfaits d’appels. 

- Déplacer les utilisateurs qui ne sont pas situés dans une région dans laquelle des plans d’appel PSTN sont disponibles vers Phone System avec un routage direct. 

- Tenez à jour une connexion RSTN aux appareils analogiques critiques d’entreprise.

Les diagrammes suivants montrent le déploiement d’origine du système hérité avec des sites distants et la migration vers un déploiement de routage direct avec l’optimisation des médias locaux :

**Déploiement hérité d’origine**  
 ![ Diagramme montrant des états avant et après](media/voice-case-study-2.png)


**Déploiement avec routage direct**

![Diagramme montrant des états avant et après](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Type de site C : combinaison de systèmes téléphoniques Skype Voix Entreprise et de systèmes de téléphonie hérités traditionnels

Contoso Skype Entreprise Voix Entreprise les numéros des utilisateurs résident sur la ligne SIP de la ligne SBC de l’opérateur. Les numéros des systèmes téléphoniques traditionnels résidant sur la ligne TDM de la passerelle PSTN.   

Contoso a basé sa décision sur les questions suivantes :

- Q. Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?<br>
  A. Non 

- Q. Devons-nous interopérables avec des systèmes PBX tiers et d’autres équipements téléphoniques ?<br> A. Non 

- Q. Devons-nous conserver notre opérateur tiers actuel ?<br> A. Non 

- Q. Devons-nous obtenir le retour sur investissement sur des SBCs déployés ?<br> A. Oui et Non  

- Q. Le plan d’appel PSTN de Microsoft est-il disponible dans cette région ?<br> A. Non 

En se basant sur les réponses à leurs questions, Contoso a décidé des solutions suivantes : 

- Pour les utilisateurs téléphoniques hérités qui seront activés pour le routage direct, Contoso a porté les numéros de la ligne TDM vers la ligne SIP pour le SBC, étant donné que le SBC est certifié pour le routage direct. 

- Pour prendre en charge un sous-ensemble d’utilisateurs qui passe au système téléphonique et pour permettre un routage continu via le système hérité, le système de téléphonie hérité a été créé comme le prochain saut vers le SBC.   

- En outre, pour encourager le changement de comportement des utilisateurs et supprimer la dépendance vis-à-vis des numéros d’extension inter et intra-sites, Contoso a fourni des conseils pour utiliser Teams pour tous les appels internes.  

Les diagrammes suivants montrent le déploiement d’origine de la version Voix Entreprise et de l’ancien système téléphonique Skype Entreprise, et la migration vers un déploiement mixte à l’aide du routage direct :

**Déploiement mixte d’origine** 
 ![ Diagramme montrant avant l’état](media/voice-case-study-4.png)

**Déploiement mixte avec routage direct** 
 ![ Diagramme montrant avant l’état](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Forfaits d’appel

Pour déterminer les configurations requises pour les plans d’appels, Contoso a examiné les principales décisions de [déploiement du plan d’appels.](calling-plan-landing-page.md#core-deployment-decisions) Les décisions qui s’en découlent ont été prises : 

- Q. Mes utilisateurs ont-ils besoin d’appels internationaux ?<br> A. Oui 

- Q. Mes utilisateurs ont-ils chacun un numéro de téléphone directement vers l’intérieur ?<br> R. Pas aujourd’hui. Tous les utilisateurs activés recevront un DID. 

- Q. Dois-je masquer ou désactiver l’ID de l’appelant ?<br> A. L’ID d’appelant d’un utilisateur est masquée sur le numéro local de Contoso. 


## <a name="direct-routing"></a>Routage direct

Contoso a participé à Ignite pour rester à jour sur les fonctionnalités d’Office 365, y compris celles disponibles avec le système téléphonique et le routage direct. Les dirigeants techniques et les architectes se sont servis des conseils fournis lors de l’édition d’Ignite 2019 pour déterminer leur direction.  Sessions clés utilisées : 

- [Planifier le succès avec le routage direct de Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Mises à jour pour le routage direct](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configuration

### <a name="calling-plans-sites"></a>Sites Forfaits d’appels

Pour obtenir des licences et attribuer des numéros de téléphone aux utilisateurs, Contoso a suivi les étapes de la procédure [Configurer les forfaits d’appels.](set-up-calling-plans.md) 

En raison du nombre d’utilisateurs devant se voir attribuer des numéros de téléphone, Contoso a décidé d’utiliser PowerShell pour affecter les numéros de téléphone. Pour découvrir comment attribuer des numéros à l’aide de PowerShell en plus d’autres paramètres, Contoso a utilisé la vue d’ensemble &mdash; &mdash; de Teams [PowerShell.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Sites de routage direct

Pour connecter l’infrastructure téléphonique locale de Contoso à Microsoft Teams, l’administrateur de Contoso a suivi les étapes de la procédure Configurer le [routage](direct-routing-configure.md) direct et examiné la vidéo [Routage](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) direct dans Microsoft Teams pour obtenir des instructions.  Contoso fait également référence à la documentation relative au déploiement du routage direct par le fournisseur SBC certifié. 

Une fois le routage direct configuré entre le système SBC et Microsoft Phone System, Contoso devait tester la configuration. Pour ce faire, les administrateurs Contoso ont utilisé le client de test SIP évoqué lors de la session Mises à jour pour le routage direct sur [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) Le script et la documentation du client test SIP ont été téléchargés à partir du script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct.   


### <a name="local-media-optimization"></a>Optimisation des médias locaux

Contoso a vu l’opportunité de tirer parti de l’optimisation des médias locaux dans les différentes régions du monde entier. Les scénarios pris en charge pour Contoso sont décrits dans l’optimisation des médias [locaux pour le routage direct.](direct-routing-media-optimization.md) La configuration de l’optimisation des médias locaux a été effectuée en suivant les conseils du fournisseur SBC et de Microsoft. Les étapes de configuration de l’optimisation des médias locaux sont les suivantes : 

- Configurer l’utilisateur et les sites SBC 

- Configurez le SBC en fonction de la spécification du fournisseur SBC, 

- Ajouter des adresses IP fiables externes à chaque site utilisé pour l’optimisation des médias locaux    

- Définir la topologie de réseau 

- Définir la topologie de réseau virtuel 

- Déterminer le mode : Toujours contourner ou uniquement pour les utilisateurs locaux 

## <a name="networking-considerations"></a>Considérations en relation avec la mise en réseau

Contoso avait un nombre d’utilisateurs qui devaient travailler à distance pendant une période prolongée après avoir été activés pour Phone System. Les utilisateurs utilisaient le vpn pour accéder à certaines applications Métier. Sur un réseau VPN, les utilisateurs du système téléphonique ont connu une dégradation de la qualité des appels. 

Pour résoudre le problème de qualité, Contoso a implémenté la tunnelliser fractionnée VPN, qui permettait à son trafic Office 365 de traverser Internet alors que la connexion aux applications internes restait sur le VPN. Pour implémenter la tunnelliser fractionnement VPN, Contoso a suivi les recommandations de la tunnelliser fractionnement [VPN pour Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)  

 





