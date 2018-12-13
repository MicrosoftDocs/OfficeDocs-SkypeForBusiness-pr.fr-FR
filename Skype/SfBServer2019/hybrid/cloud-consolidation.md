---
title: Consolidation de cloud pour les équipes et Skype pour les entreprises
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cet article décrit comment parvenir à cette consolidation pour les organisations comptant deployment(s) locale de Skype pour les professionnels (ou Lync) qui cherchent à déplacer pour déplacer leur charge de travail de communications unifiées pour les équipes ou Skype pour Business Online.
ms.openlocfilehash: 09a19b884b67f9d6c3dbbe552f2576b6b5e68674
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247653"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Consolidation de cloud pour les équipes et Skype pour les entreprises

> [!Note]
> Ceci est une préversion ou une fonctionnalité d'une publication anticipée. 

De nombreuses grandes entreprises ont plus d’un local forêt Active Directory et dans certains cas, les clients disposent de plusieurs Exchange et/ou Skype pour le déploiement de serveur d’entreprise (ou Lync Server). En outre, toutes les organisations qu’une seule forêt locale peuvent trouver eux-mêmes dans une situation similaire par le biais d’une entreprise fusion ou acquisition. Comme ces clients déplacement vers le nuage, qu’ils souhaitent consolider les plusieurs instances d’une charge de travail donné local dans le nuage en un seul client Office 365. Cet article décrit comment parvenir à cette consolidation pour les organisations comptant plusieurs déploiements sur site de Skype d’entreprise (ou Lync) qui souhaitent déplacer leur charge de travail UC vers le nuage Microsoft, par exemple, Microsoft Teams et/ou Skype pour Business Online.

Les instructions historiquement, pour les clients dans cette situation à consolider tout d’abord les déploiements sur site et le déplacer ensuite vers le nuage. Alors que ce soit toujours une option, cet article décrit une solution basée sur les nouvelles fonctionnalités qui permet aux organisations avec plusieurs Skype pour les déploiements d’entreprise pour migrer un déploiement à la fois dans un seul client Office 365, sans effectuer sur site consolidation de serveurs. Notez que même avec cette nouvelle fonctionnalité Skype pour Business Online et Microsoft Teams ne prennent pas charge Skype plusieurs forêts Business/Lync en mode hybride avec un seul client Office 365. 

> [!Important]
> Avant d’utiliser ce guide pour la configuration, veillez à passer en revue et de comprendre les [Limitations](#limitations), comme elles peuvent affecter votre organisation.

## <a name="overview-of-cloud-consolidation"></a>Vue d’ensemble de la consolidation de nuage

Consolidation de tous les utilisateurs sur site dans le nuage dans un seul client Office 365 peut être réalisée pour une organisation avec plusieurs Skype pour les déploiements d’entreprise, à condition que les conditions clées suivantes sont remplies :

- Il doit exister au maximum un client Office 365 impliqués. Consolidation de serveurs dans les scénarios avec plus d’un client Office 365 n’est pas pris en charge.
- À un moment donné, une seule locale Skype pour la forêt de l’entreprise peut être en mode hybride (Shared SIP espace d’adressage). Tous les autres Skype sur site pour les forêts d’entreprise doit demeurer locale (et sans doute fédérée avec eux). Notez que ce autres locaux organisations *peuvent* synchroniser avec DAS si vous le souhaitez avec les [nouvelles fonctionnalités pour désactiver les domaines SIP en ligne](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) disponibles à compter de décembre 2018.

Clients de déploiements de Skype pour les entreprises dans plusieurs forêts entièrement migrer tous les utilisateurs d’un seul hybride Skype pour la forêt Business individuellement dans le client Office 365 à l’aide des fonctionnalités de l’espace d’adressage SIP partagé et désactiver puis hybride avec qui déploiement sur site, avant de passer à migrer la prochaine locale Skype pour le déploiement d’entreprise. Avant sont migrées vers le nuage, les utilisateurs locaux restent dans un état fédéré avec tous les utilisateurs qui ne sont pas représentés dans le même répertoire de l’utilisateur local.  

## <a name="canonical-example-of-cloud-consolidation"></a>Exemple canonique de consolidation de nuage

Envisagez une organisation avec deux distinct fédérés déploiements sur site de Skype pour les entreprises qui souhaite consolider en ligne dans Microsoft Teams ou Skype pour Business Online.


|Détails de l’état d’origine |Détails de l’état souhaité |
|---------|---------|
|<ul><li>2 Skype indépendant pour les entreprises déploiements dans des forêts distinctes AD sur site<li>Au maximum 1 forêt est dans un déploiement hybride avec Skype pour Business Online <li> Développées sont fédérées avec eux <li>Les utilisateurs ne sont pas synchronisés entre les forêts<li> L’organisation peut avoir un client Office 365 et peut être la synchronisation leur répertoire dans Azure AD</ul>|<ul> <li>1 client office 365<li>Ne plus déploiements locaux, donc aucun hybride restant<li>Tous les utilisateurs sur site sont hébergés sur Skype pour Business en ligne et peuvent être éventuellement équipes uniquement des utilisateurs <li>N’importe où aucun encombrement locale de Skype pour les entreprises <li>Les utilisateurs ont toujours l’authentification locale</ul> |

![Consolidation des deux distinct fédérés déploiements sur site](../media/cloudconsolidationfig1.png)  

Les étapes de base pour obtenir de l’état d’origine à l’état final souhaité sont inférieurs.  Notez que certaines organisations peuvent estimer que leur point de départ se situe au milieu de ces étapes. Voir d' [autres points de départ](#other-starting-points), plus loin dans cet article. Enfin, dans certains cas, l’ordre pouvant être ajusté, en fonction des besoins. [Limitations et contraintes de clé](#limitations) sont décrites plus loin.

1.  Obtenir un client Office 365 s’il n’existe pas encore.
2.  Assurez-vous que tous les domaines SIP pertinents parmi les deux déploiements locaux sont vérifiés domaines d’Office 365.
3.  Choisissez un Skype pour le déploiement d’entreprise qui est hybride avec Office 365. Dans cet exemple, nous allons utiliser OriginalCompany. <span>com.
4.  [Activer DAS Connect pour la forêt](configure-azure-ad-connect.md) qui deviendront des premiers hybride (OriginalCompany.<span> com). 
5.  Si vous lancerons équipes dans votre organisation, définissez la stratégie de client à l’échelle pour [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) SfBWithTeamsCollab ou une des autres modes SfB (SfBOnly ou SfBWithTeamsCollabAndMeetings). Cela est essentielle pour garantir le routage des appels et conversations des utilisateurs qui se connectent aux équipes uniquement pour les utilisateurs qui restent sur site.
6.  Il est recommandé à ce stade (mais pas encore requise jusqu'à l’étape 11) pour [Activer DAS Connect pour l’autre forêt](cloud-consolidation-aad-connect.md) (AcquiredCompany.<span> com). En supposant que DAS connexion est activée dans les deux forêts, la société ressemble à **[La Figure A](#figure-a)**, qui peut être un point de départ commun pour certains développées. 
7.  Pour tous les domaines SIP hébergés par les autres déploiements locaux (dans ce cas, AcquiredCompany.<span> com), à l’aide de [désactiver ces domaines SIP dans Skype pour Business Online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) `Disable-CsOnlineSipDomain` dans PowerShell. (Il s’agit de nouvelles fonctionnalités à compter de décembre 2018.)
8.  [Configurer les Skype pour un environnement hybride Business](configure-federation-with-skype-for-business-online.md) pour OriginalCompany. <span>com (l’un déploiement toujours a activé les domaines SIP en ligne).
9.  Dans le déploiement hybride (OriginalCompany.<span> com), démarrer [le déplacement d’utilisateurs de Skype pour les entreprises dans les locaux vers le nuage](move-users-between-on-premises-and-cloud.md) (si les équipes uniquement ou non) afin que le compte est hébergé dans Skype pour Business Online. L’organisation ressemble maintenant à **[La Figure B](#figure-b)**. Les modifications de clé de la Figure A sont les suivants :
    - Les utilisateurs dans les deux annuaires locaux sont désormais dans DAS.
    - AcquiredCompany. <span>com est un domaine SIP en ligne désactivé.
    - Certains utilisateurs ont été déplacés en ligne à deux Skype pour Business Online ou équipes. (Voir a utilisateur violet)
10. Une fois que tous les utilisateurs sont déplacés vers le nuage, [désactiver hybride avec le Skype pour le déploiement local de Business](cloud-consolidation-disabling-hybrid.md) pour OriginalCompany. <span>com à partir d’Office 365 :  
    - Désactiver le domaine fractionné dans le client Office 365.
    - Désactiver la possibilité de communiquer avec Office 365 dans OriginalCompany. <span>com local.
    - Mettre à jour les enregistrements DNS pour OriginalCompany. <span>com pour pointer vers Office 365.
11. Si ne pas déjà fait, [Activer DAS Connect pour la forêt suivante](cloud-consolidation-aad-connect.md) qui seront dirigés hybride (AcquiredCompany.<span> com). À ce stade, l’organisation ressemble à **[La Figure C](#figure-c)**. Cela peut être un autre point de départ commun pour certaines organisations. 
12. Dans PowerShell, [Activer les domaines SIP pour le déploiement local suivant](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) qui seront dirigés hybride, AcquiredCompany. <span>com. Cette opération est effectuée à l’aide `Enable-CsOnlineSipDomain`, qui est une nouvelle fonctionnalité disponible à compter de décembre 2018.
13. Si vous utilisez la fédération fermée, vous devez ajouter les domaines SIP (à l’exclusion de *. microsoftonline.com) du client en ligne pur en tant que domaines autorisés dans la **même** Office 365. Notez qu’il peut prendre un certain temps avant la modification prend effet et il n’existe aucun inconvénient à cela au début, nous vous recommandons de procéder bien avant de passer à l’étape 14.
14. Mettre à jour l’environnement local pour accepter tous les domaines SIP à partir du client en ligne, de sorte qu’ils correspondent.
    - [Mettre à jour le SAN dans tous les certificats de périphérie](cloud-consolidation-edge-certificates.md) à la même valeur que précédemment, ainsi que les valeurs pour tous les domaines SIP en ligne existantes (sauf *. microsoftonline.com), dans ce cas, Sip.OriginalCompany. <span>com.
    - Assurez-vous que OriginalCompany. <span>com est un [autorisés du domaine](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) dans le déploiement local, AcquiredCompany. Ajouter des domaines autorisés.
15. [Activer les Skype pour un environnement hybride Business](configure-federation-with-skype-for-business-online.md) entre AcquiredCompany local. <span>com et le nuage.
16. Comme vous le souhaitez, [faites migrer les utilisateurs sur site vers le nuage](move-users-between-on-premises-and-cloud.md). Vous pouvez migrer des utilisateurs directement à [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) mode ou vous pouvez migrer tout d’abord vers Skype pour Business Online. Au cours de cet état, l’organisation ressemble à **[La Figure D](#figure-d)**.
17. Une fois que tous les utilisateurs sont migrés, [désactiver hybride avec l’environnement local](cloud-consolidation-disabling-hybrid.md) pour *rendre le nuage pure organisation*!

Les diagrammes ci-dessous indiquent la configuration à différents points clés pendant ce processus.

##### <a name="figure-a"></a>Figure a :

- Les deux synchronisation organisations via DAS Connect, DAS a désormais tous les utilisateurs des deux déploiements locaux.
- Tous les utilisateurs hébergés sur site.  
- Skype pour Business hybride n’est *pas* encore configuré.
- Si les utilisateurs dans un déploiement équipes, ils ne pourront pas se fédérer avec eux (ou toute organisation), ni qu’ils auront l’interopérabilité avec n’importe quel Skype pour les utilisateurs professionnels. Dans cette étape, Microsoft recommande l’utilisation d’équipes pour canaux uniquement.<br><br>
    ![Diagramme de la figure A](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figure b :

- AcquiredCompany. <span>com est un domaine [désactivé](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) online SIP. Tous les utilisateurs sont en local. S’ils utilisent des équipes, ils n’ont pas la fédération ou l’interopérabilité. Dans cette étape, Microsoft recommande l’utilisation d’équipes pour canaux uniquement.
- Skype pour Business hybride a été activé pour une des organisations locales.
- Certains utilisateurs dans l’organisation hybride ont été déplacés vers le nuage (l’utilisateur A, comme indiqué par la trame de fond violet). Ces utilisateurs peuvent être Skype pour les utilisateurs professionnels en ligne ou équipes uniquement des utilisateurs avec interopérabilité complète et prise en charge de la fédération.<br><br>
    ![Diagramme de la figure B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figure c :

- Tous les utilisateurs à partir de OriginalCompany. <span>com figurent désormais dans le nuage (hébergé dans Skype pour Business Online). Il est recommandé que leur également être équipes uniquement.
- Skype pour la configuration hybride Business avec la OriginalCompany. <span>déploiement com a été désactivé. Le déploiement local n’apparaît plu.
- Si AcquiredCompany. <span>com n’a pas été précédemment la synchronisation DAS, continuer à partir d’ici il doit être synchronisé maintenant. Mais il n’est pas encore hybride (espace d’adressage SIP partagé), et jusqu'à ce que l’organisation est prête à passer à l’environnement hybride, le domaine SIP en ligne pour l’organisation pur locale (AcquiredCompany.com) doit rester désactivé, afin que les utilisateurs équipes online peuvent communiquer avec les utilisateurs locaux.<br><br>
    ![Diagramme de la figure C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figure d :

- AcquiredCompany. <span>com est désormais activée comme domaine SIP en ligne.
- Sur site est mis à jour pour accepter OriginalCompany. <span>com. (Les deux autorisés domaine et certificats de périphérie sont mis à jour).
- Espace d’adressage SIP partagé est activée entre AcquiredCompany. <span>com et client Office 365.
- Certains utilisateurs dans l’organisation hybride peuvent ont été déplacés vers le nuage, tels que D utilisateur ci-dessous (indiqué par la trame de fond violet).<br><br>
    ![Diagramme de la Figure D](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Autres points de départ

L’exemple canonique ci-dessus suppose que l’organisation commence par deux fédérés déploiements locaux avec aucune présence d’Office 365. Cependant, certaines organisations peuvent avoir une empreinte Office 365 existante, et il peut y avoir des points d’entrée différents dans la séquence ci-dessus. Il existe quatre configurations standard :

- Plusieurs organisations fédérées locale avec aucun client Office 365. Dans ce cas, commencez à l’étape 1.
- Plusieurs organisations fédérées locaux qui sont déjà en cours de synchronisation plusieurs Skype pour la forêt d’entreprise dans une seule annonce Azure des clients. Une telle organisation ressemble à l’organisation hypothétique dans la Figure A, qui a effectué les étapes 1 à 6 et doit commencer à l’étape 7.
- Une organisation hybride qui se fédère avec 1 ou plusieurs autres pur organisations locales, aucun d'entre eux synchroniser DAS. Une telle organisation ressemble à l’organisation hypothétique dans **La Figure E**, indiqué ci-dessous.
    - Cette organisation est similaire à la Figure B, qui a terminé les étapes 1 à 9, à l’exception :
        - Son Skype non hybrides pour les déploiements d’entreprise ne sont *pas* encore en cours de synchronisation pour Azure AD.
        -  Domaines SIP en ligne ne sont pas encore désactivés. 
    - Ces organisations doivent soit :
        - Effectuer la migration de l’organisation hybride existant, puis entrez la séquence ci-dessus à l’étape 10.  OR,
        - S’il est nécessaire de synchroniser n’importe quelle autre Skype pour les forêts Business dans DAS avant la fin de la migration de l’organisation hybride, puis l’organisation doit effectuer l’étape 7 (désactiver online tous les domaines SIP dans n’importe quel autre Skype sur site pour le déploiement d’entreprise qui seront synchronisation en DAS) et activer la connexion DAS et uniquement puis passez à l’étape 10 (mettre hors service le déploiement hybride d’origine).       
                **Figure E**<br>
                ![Diagramme de la figure E](../media/cloudconsolidationfige.png)
- Skype pure organisation Business Online (qui peut ou n’utilise pas les équipes) se fédère avec un Skype local séparé pour l’organisation de l’entreprise. Une fois cette organisation désactive le domaine SIP en ligne pour l’organisation locale et permet de connecter DAS pour le Skype local pour l’organisation de l’entreprise, il ressemble à l’organisation hypothétique illustrée à la **[Figure C](#figure-c)** qui a effectué les étapes 1-11.

## <a name="limitations"></a>Limitations

- Il doit exister au maximum un client Office 365 impliqués. Consolidation de serveurs dans les scénarios avec plus d’un client Office 365 n’est pas pris en charge.
- Une seule locale Skype pour la forêt de l’entreprise peut être en mode hybride (espace d’adressage SIP partagé) à la fois. Tous les autres locaux Skype pour les forêts d’entreprise doit demeurer purement local et doit être fédéré entre eux et le client Office 365.
- Avant d’en cours de migration vers le nuage, il existe une expérience asymétrique pour les utilisateurs dans ce déploiement, pas tous les utilisateurs en ligne étant représenté locale :
    - L’expérience peut être résumée comme suit :
        - Tous les utilisateurs hébergement en ligne interagiront avec les utilisateurs locaux dans l’environnement hybride comme si l’utilisateur est hybride.
        - Interaction des utilisateurs locaux dans le déploiement hybride avec des utilisateurs en ligne qui sont représentées dans son propre répertoire local comme s’ils étaient hybride. 
        - Interaction des utilisateurs dans le déploiement hybride avec des utilisateurs en ligne qui ne sont pas représentés dans local AD sur site comme fédérés.
    - Dans **[La Figure D](#figure-d)** ci-dessus, l’utilisateur E est local dans AcquiredCompany. <span>com.  Utilisateur E interagit avec l’utilisateur D (hébergé en ligne) à l’aide de l’expérience hybride standard, mais utilisateur E aura une expérience fédérée avec des utilisateurs A, B et C, car ils ne sont pas représentés dans le répertoire local. Toutefois, les utilisateurs A, B et C interagiront avec utilisateur E comme si l’utilisateur était dans hybride.
    - Implications de l’interaction en cours hybride et fédération :
        - Présence n’est pas automatiquement abonnée à pour les utilisateurs fédérés, sauf si l’utilisateur est marqué en tant que contact.
        - Le transfert d’appel ne fonctionne pas entre domaines fédérés.
        - Scénarios de transfert d’appel sont plus limitées.
        - Limitation peut être appliquée au trafic fédéré.
- Étant donné cette expérience asymétrique, prise en charge officielle pour appeler les fonctionnalités de scénarios intersite entre un utilisateur local et qu’un utilisateur dans le nuage pas dans le répertoire local est limitée uniquement d’égal à égal. 
    - Appelez le transfert, transfert, files d’attente des appels, etc. entre ces utilisateurs n’est pas pris en charge.
    - Ces scénarios d’appel non pris en charge apparaît toujours activés, mais dans de nombreux cas ils échouent de manière aléatoire. 
    - Dans **[La Figure D](#figure-d)** ci-dessus, utilisateur E est sur site et appels avec des utilisateurs A, B ou C pris en charge uniquement en tant que d’égal à égal. (Appels avec utilisateur D n’auraient pas de limitations de la prise en charge).  Toutefois, une fois que l’utilisateur local E est déplacé vers le nuage, cette restriction ne s’applique.
- Si vous avez plusieurs déploiements de Skype pour Business Server 2019 dans votre environnement, 1 seul de ces déploiement peut être configuré pour utiliser d’organisation standard automatique, car cette fonctionnalité nécessite Skype pour que la configuration hybride Business Server. 
- Vous pouvez ajuster l’ordre de certaines des étapes précédentes. La condition clée qui doit être remplie est que si tous ces éléments sont vraies :
    - Plusieurs locaux Skype pour la synchronisation de forêt métiers à un seul client DAS
    - Domaine fractionné est activé avec une seule forêt locale
    - Au moins un utilisateur dans l’organisation hybride a été migré vers le nuage<br>   Ensuite, vous *devez* désactiver tous les autres domaines SIP en ligne à partir de n’importe quel autre Skype local pour la forêt de l’entreprise. Dans le cas contraire, la fédération entre les utilisateurs dans utilisateurs sur site et organisation hybride dans d’autres organisations en ligne rompra dans une direction.

## <a name="implications"></a>Implications en matière de

- Car il existe des limitations de la prise en charge des fonctions d’appel avancées comme indiqué ci-dessus, **organisations doivent traiter ces États asymétriques comme temporaires dans le cadre de la migration et pas les adopter en tant que l’état stable**.  
- Organisations avec plusieurs Skype sur site pour les déploiements d’entreprise doivent généralement commencer avec un déploiement qui peut être entièrement migré vers le nuage, afin que la consolidation peut continuer. Il est entendu que dans certains cas, il sera holdouts de certains groupes d’utilisateurs pour lesquels il n’est pas encore viable pour atteindre les équipes. Lorsqu’il s’agit d’un compte dans les scénarios impliquant plusieurs Skype pour les forêts Business, commencer la migration avec une autre forêt qui ne dispose pas de ces limites, si possible.
- Lors du déplacement local vers le nuage, les utilisateurs qui ont des relations de délégation et/ou sont généralement sont impliqués dans le transfert d’appel scénarios doivent être déplacées ensemble comme une unité.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considérations relatives au passage en mode TeamsOnly

Lorsque vous déplacez des utilisateurs sur site vers le nuage dans un environnement hybride, vous pouvez les déplacer vers le Skype pour le mode entreprise uniquement ou TeamsOnly. *Si vous prévoyez de déplacer des utilisateurs vers le mode TeamsOnly, veillez à lire en premier de cette section.*

- Lorsque vous affectez le mode TeamsOnly à un utilisateur, toutes les conversations et les appels à partir de n’importe quel autre utilisateur est alors placé dans le client des équipes de cet utilisateur. 
- Pour garantir un routage correct de conversations et appels entre les utilisateurs qui sont TeamsOnly et les utilisateurs qui utilisent encore Skype pour les entreprises en local, vous devez vous assurer que les utilisateurs locaux ont TeamsUpgradePolicy avec un des modes SfB, plutôt que des îles (qui est la valeur par défaut ). 
    - Pour ce faire, *que vous devez d’abord définir instance globale de votre client de TeamsUpgradePolicy à une des valeurs suivantes*:
        - SfBWithTeamsCollab (recommandé)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Vous pouvez accorder la stratégie au niveau du client à l’aide de cette commande :<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Remarque : Actuellement, vous devez le faire au niveau du client à l’échelle, car la stratégie ne peut pas être affectée à des utilisateurs individuels qui n’ont pas une adresse SIP dans le répertoire en ligne. Alors que vous avez désactivé les domaines SIP en ligne pour votre deployment(s) pur localement, les utilisateurs dans ces domaines n’auront des adresses SIP dans le répertoire en ligne par sa conception. Par conséquent, le seul moyen pour appliquer la stratégie aux utilisateurs sur site est en affectant au niveau du client. En revanche, dans le hybride déploiement les utilisateurs auront une adresse SIP dans le répertoire en ligne afin qu’ils peuvent être assignées explicitement une stratégie s’il est nécessaire qu’ils possèdent une valeur différente de la stratégie globale du client.
- Le client équipes UX ne respecte pas encore les modes SfB de TeamsUpgradePolicy. Par exemple, lorsque dans ces modes, initiation d’appel et de conversation dans les équipes est actuellement possible, bien qu’à l’avenir, cela n’est pas le cas. Cela peut entraîner la confusion parmi les utilisateurs, car les réponses peuvent parfois atteindre des équipes parfois Skype pour les entreprises, selon les circonstances. Il est recommandé que vous désactivez les appels séparément et conversation via TeamsMessagingPolicy et TeamsCallingPolicy pour les utilisateurs qui sont toujours en local.

## <a name="see-also"></a>Voir aussi

[Mettre à jour le certificat de serveur edge](cloud-consolidation-edge-certificates.md)

[Mise à jour DAS se connecter à inclure plusieurs forêts](cloud-consolidation-aad-connect.md)

[Désactiver hybride pour effectuer la migration vers le nuage](cloud-consolidation-disabling-hybrid.md)