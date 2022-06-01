---
title: 'Étude de cas Contoso : Système téléphonique pour une société multinationale'
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
description: 'Teams étude de cas de voix pour une société multinationale : système téléphonique'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823665"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Étude de cas Contoso : Système téléphonique pour une société multinationale

Selon l’emplacement géographique et d’autres facteurs, Contoso avait des bureaux utilisant les solutions de téléphonie suivantes :

- Type de site A : Skype Entreprise Voix Entreprise

- Type de site B : systèmes de téléphonie hérités traditionnels

- Type de site C : combinaison de Skype Entreprise Voix Entreprise et de systèmes de téléphonie hérités traditionnels


Pour implémenter une solution système Téléphone Microsoft pour l’ensemble de son organisation, Contoso devait déterminer&mdash;, pour chaque type&mdash;de site, les options suivantes qui seraient utilisées avec Système téléphonique pour se connecter au réseau téléphonique commuté (RTC) :

- Système téléphonique avec forfait d’appels 

- Système téléphonique avec son propre opérateur RTC via le routage direct 

- Combinaison de Système téléphonique avec forfait d’appels et Système téléphonique avec un propre opérateur RTC via le routage direct
 
Pour déterminer la solution appropriée pour leur organisation, Contoso a utilisé [Planifier votre solution vocale Teams](/microsoftteams/cloud-voice-landing-page) et l’appel de session Ignite 2019 [dans Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Type de site A : Skype Entreprise Voix Entreprise 

Contoso Skype Entreprise Voix Entreprise a été configuré en tant que hub-and-spoke. Il y avait un emplacement central qui maintenait la passerelle RTC dans la région qui fournissait la connexion au RTC pour les utilisateurs Skype Entreprise Voix Entreprise dans le pays. Souvent, ces bureaux satellites n’avaient pas leur propre sortie Internet. Les numéros de ces utilisateurs se trouvent sur la jonction SIP qui se connecte à un SBC existant. 

Pour déterminer si le SBC déjà déployé est certifié pour le routage direct et le contournement multimédia, Contoso a vérifié la [liste des contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).  

Les habitudes de numérotation de l’utilisateur étaient de composer un utilisateur sur le système de téléphonie hérité à l’aide d’une extension, même lorsque l’utilisateur dispose d’un client Skype Entreprise disponible pour l’audio P2P. 

Contoso a basé sa décision sur les questions suivantes :

- Q. Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?<br>
  Un. Non 

- Q. Devons-nous interagir avec des systèmes PBX tiers et d’autres équipements de téléphonie ?<br>
  Un. Non 

- Q. Devons-nous conserver notre transporteur tiers actuel?<br> Un. Oui (pays réglementés) et Non 

- Q. Devons-nous déployer le roi sur les SBC ?<br> Un. Oui et non  

- Q. Les forfaits d’appels RTC Microsoft sont-ils disponibles dans cette région ?<br> Un. Oui et non 

En fonction des réponses à leurs questions, Contoso a décidé de :

- Déplacez les utilisateurs situés dans une région où les plans d’appels RTC sont disponibles pour Système téléphonique avec des plans d’appel. 

- Déplacez les utilisateurs qui ne se trouvent pas dans une région où les forfaits d’appels RTC sont disponibles, les utilisateurs situés dans un site où le retour sur investissement sur les SBC n’a pas encore été atteint et les utilisateurs résidant dans un pays qui a des réglementations de téléphonie à Système téléphonique avec le routage direct. 

Le diagramme suivant montre le déploiement initial Skype Entreprise Voix Entreprise et comment ce déploiement a été migré vers les plans d’appel Microsoft et le routage direct :

![Diagramme montrant les états avant et après.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Type de site B : systèmes de téléphonie hérités traditionnels

Contoso avait de nombreux bureaux qui exploitaient des systèmes de téléphonie hérités. Il y avait un sous-ensemble d’utilisateurs qui avaient un numéro de téléphone E1.64 tandis que d’autres n’avaient qu’une extension. Ces nombres se trouvent sur la jonction TDM à la passerelle PSTN. La numérotation intrasite a été configurée en tirant parti d’un code de site devant l’extension pour déterminer où acheminer l’appel. Les habitudes de numérotation des utilisateurs étaient de composer par extension.   

Contoso a basé sa décision sur les questions suivantes :

- Q. Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?<br>
  Un. Non 

- Q. Devons-nous interagir avec des systèmes PBX tiers et d’autres équipements de téléphonie ?<br> Un. Oui

- Q. Devons-nous conserver notre transporteur tiers actuel?<br> Un. Non 

- Q. Le forfait d’appels rtc Microsoft est-il disponible dans notre région ?<br> Un. Oui et non 

En fonction des réponses à leurs questions, Contoso a décidé de : 

- Déplacez les utilisateurs situés dans une région où les plans d’appels RTC sont disponibles pour Système téléphonique avec des plans d’appel. 

- Déplacez les utilisateurs qui ne se trouvent pas dans une région où les plans d’appels RTC sont disponibles pour Système téléphonique avec le routage direct. 

- Conservez une connexion RTC à des appareils analogiques critiques pour l’entreprise.

Les diagrammes suivants montrent le déploiement du système hérité d’origine avec des sites distants et la migration vers un déploiement de routage direct avec optimisation des médias locaux :

**Déploiement hérité d’origine** 
![ Un diagramme montre les états avant et après.](media/voice-case-study-2.png)


**Déploiement avec routage direct**

![Diagramme montrant les états avant et après.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Type de site C : combinaison de Skype Entreprise Voix Entreprise et de systèmes de téléphonie hérités traditionnels

Contoso Skype Entreprise Voix Entreprise les numéros des utilisateurs résident sur la jonction SIP vers le SBC à partir du transporteur. Les numéros des systèmes de téléphonie traditionnels résidaient sur la jonction TDM à la passerelle RTC.   

Contoso a basé sa décision sur les questions suivantes :

- Q. Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?<br>
  Un. Non 

- Q. Devons-nous interagir avec des systèmes PBX tiers et d’autres équipements de téléphonie ?<br> Un. Non 

- Q. Devons-nous conserver notre transporteur tiers actuel?<br> Un. Non 

- Q. Devons-nous déployer le roi sur les SBC ?<br> Un. Oui et non  

- Q. Le plan d’appels RTC de Microsoft est-il disponible dans cette région ?<br> Un. Non 

En fonction des réponses à leurs questions, Contoso a décidé des points suivants : 

- Pour les utilisateurs de téléphonie hérités qui seront activés pour le routage direct, Contoso a porté les numéros de la jonction TDM vers la jonction SIP pour le SBC, car le SBC est certifié pour le routage direct. 

- Pour prendre en charge un sous-ensemble d’utilisateurs qui passent à Système téléphonique et permettre le routage continu via le système hérité, le système de téléphonie hérité a été configuré comme tronçon suivant du SBC.   

- En outre, pour encourager le changement de comportement de l’utilisateur et supprimer la dépendance à l’égard de la numérotation des extensions intersites et intrasite, Contoso a fourni des conseils pour utiliser Teams pour tous les appels internes.  

Les diagrammes suivants montrent l’Skype Entreprise Voix Entreprise d’origine et le déploiement du système de téléphonie hérité, ainsi que la migration vers un déploiement mixte à l’aide du routage direct :

**Déploiement mixte d’origine**
![ Diagramme 1 montrant l’état avant.](media/voice-case-study-4.png)

**Déploiement mixte avec routage**
![ direct Diagramme 2 montrant l’état avant.](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Forfaits d’appel

Pour déterminer les exigences de configuration pour les plans d’appel, Contoso a examiné les [décisions de déploiement principales du plan d’appel](calling-plan-landing-page.md#core-deployment-decisions). Les décisions qui en résultent ont été prises : 

- Q. Mes utilisateurs ont-ils besoin d’appels internationaux ?<br> Un. Oui 

- Q. Mes utilisateurs disposent-ils chacun d’un numéro de téléphone DID directement entrant ?<br> R. Pas aujourd’hui. Tous les utilisateurs activés recevront un DID. 

- Q. Dois-je masquer ou désactiver l’ID de l’appelant ?<br> Un. L’ID d’appelant d’un utilisateur est masqué sur le numéro local de Contoso. 


## <a name="direct-routing"></a>Routage direct

Contoso a assisté à Ignite pour rester à jour sur Office 365 fonctionnalités, notamment celles disponibles avec Téléphone système et le routage direct. Le leadership technique et les architectes ont utilisé les conseils fournis lors de l’Ignite 2019 pour déterminer leur orientation.  Sessions clés utilisées : 

- [Planifier la réussite du routage direct Microsoft Teams](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [Mises à jour pour le routage direct](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>Configuration

### <a name="calling-plans-sites"></a>Sites de forfaits d’appels

Pour obtenir des licences et attribuer des numéros de téléphone aux utilisateurs, Contoso a suivi les étapes décrites dans [Configurer les forfaits d’appels](set-up-calling-plans.md). 

En raison du nombre d’utilisateurs qui devaient se voir attribuer des numéros de téléphone, Contoso a décidé d’utiliser PowerShell pour attribuer les numéros de téléphone. Pour savoir comment attribuer des nombres à l’aide de PowerShell&mdash;en plus d’autres paramètres&mdash;, Contoso a utilisé la [vue d’ensemble Teams PowerShell](teams-powershell-overview.md).  

### <a name="direct-routing-sites"></a>Sites de routage direct

Pour connecter l’infrastructure de téléphonie locale de Contoso à Microsoft Teams, l’administrateur de Contoso a suivi les étapes de [configuration du routage direct](direct-routing-configure.md) et a examiné le [routage direct vidéo dans Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) pour obtenir des conseils.  Contoso a également fait référence à la documentation sur le déploiement du routage direct par le fournisseur SBC certifié. 

Une fois le routage direct configuré entre le SBC et Téléphone Microsoft System, Contoso a dû tester la configuration. Pour ce faire, les administrateurs de Contoso ont utilisé le client SIP Tester qui a été abordé dans la [session « Mises à jour pour le routage direct à Ignite 2019](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138). Le script client et la documentation du testeur SIP ont été téléchargés à partir du script PowerShell pour tester les connexions du contrôleur de frontière de session de routage direct.   


### <a name="local-media-optimization"></a>Optimisation des médias locaux

Contoso a vu l’opportunité de tirer parti de l’optimisation des médias locaux dans les différentes régions du monde. Les scénarios pris en charge pour Contoso sont décrits dans [Optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md). La configuration de l’optimisation des médias locaux a été effectuée en suivant les conseils du fournisseur SBC et de Microsoft. Les étapes de configuration pour l’optimisation des médias locaux sont les suivantes : 

- Configurer l’utilisateur et les sites SBC 

- Configurez le SBC en fonction de la spécification du fournisseur SBC, 

- Ajouter des adresses IP approuvées externes à chaque site utilisé pour l’optimisation des médias locaux    

- Définir la topologie de réseau 

- Définir la topologie de réseau virtuel 

- Déterminer le mode : Toujours contourner ou uniquement pour les utilisateurs locaux 

## <a name="networking-considerations"></a>Considérations relatives à la mise en réseau

Contoso avait un certain nombre d’utilisateurs qui devaient travailler à distance pendant une période prolongée après avoir été activés pour Système téléphonique. Les utilisateurs ont utilisé le VPN pour accéder à certaines applications métier. Sur VPN, les Système téléphonique utilisateurs ont subi une dégradation de la qualité des appels. 

Pour résoudre le problème de qualité, Contoso a implémenté le tunneling fractionné VPN, qui a permis à son trafic Office 365 de traverser Internet pendant que la connexion aux applications internes restait sur le VPN. Pour implémenter le tunneling fractionné VPN, Contoso a suivi les instructions de [l’implémentation du tunneling fractionné VPN pour Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).  

