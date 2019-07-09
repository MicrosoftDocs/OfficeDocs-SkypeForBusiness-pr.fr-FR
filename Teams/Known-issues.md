---
title: Problèmes connus pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 6/25/2019
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: marcl
localization_priority: Priority
search.appverid: MET150
description: Liste actuelle des problèmes connus pour l'application client et l'expérience administrateur de Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 843a8f5f2ea960f711d1b4160186957b1c4b306e
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588086"
---
# <a name="known-issues-for-microsoft-teams"></a>Problèmes connus pour Microsoft Teams

Cet article répertorie les problèmes connus concernant Microsoft Teams, par fonctionnalité spécifique.

## <a name="administration"></a>Administration



|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les journaux d’audit peuvent indiquer un nom d’utilisateur incorrect comme initiateur lorsqu’une personne a été supprimée de Teams  <br/> |Une équipe Teams est un groupe moderne dans AAD. Lorsque vous ajoutez/supprimez un membre par l’intermédiaire de l'interface utilisateur de Teams, le flux sait exactement quel utilisateur a initialisé la modification, et le journal d’audit reflète les informations correctes. Cependant, si un utilisateur ajoute ou supprime un membre via AAD, la modification est synchronisée sur le serveur principal de Teams sans indiquer à Teams qui a initialisé l’action. Microsoft Teams sélectionne le premier propriétaire de Teams comme initiateur, ce qui est finalement répercuté dans le journal d’audit également.    <br/> |  <br/> |11/05/2018  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La stratégie EAF dans le kit de ressources pour une expérience de migration améliorée (EMET) peut identifier de manière incorrecte les optimisations du sandbox Chromium comme des menaces. <br/> |Un problème a été identifié avec le sandbox Chromium, la stratégie de filtrage de l’accès à la table d’exportation des adresses (EAF) dans le kit de ressources pour une expérience de migration améliorée (EMET) et dans la protection avancée contre les menaces Windows Defender (ATP) pouvant identifier de manière incorrecte les optimisations du sandbox Chromium comme des menaces. Cela entraîne un fonctionnement incorrect de Teams.  <br/> | Pour résoudre ce problème, désactivez EAF pour Teams. Vous trouverez plus d'informations sur le problème dans les [Directives d’atténuation EMET](https://support.microsoft.com/fr-FR/help/2909257/emet-mitigations-guidelines) Pour des informations complémentaires sur Windows Defender ATP et la stratégie EAF, reportez-vous à la rubrique [Personnaliser la protection contre les attaques](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/customize-exploit-protection) <br/> |11/10/2018 <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible d’ajouter des membres aux équipes lorsque UsersPermissionToReadOtherUsersEnabled est défini sur false  <br/> |Lorsque cette valeur est définie sur false dans AAD, le client ne peut pas ajouter de membres internes ou externes dans Microsoft Teams, et le message d’erreur suivant s’affiche : « Nous n’avons pas pu ajouter le membre. Nous avons rencontré un problème. Réessayez ultérieurement. » Cependant, des membres peuvent être ajoutés directement à des groupes Office 365.    <br/> |Définissez ce paramètre sur true dans AAD.  <br/> |10/04/18  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La gestion des administrateurs des connecteurs à l’échelle du client n’est plus disponible  <br/> |Lorsque l’on tente d’ajouter un connecteur dans le client et la version en ligne, l’erreur suivante s’affiche : Une erreur inattendue s'est produite. Veuillez réessayer. Set-OrganizationConfig -ConnectorsEnabled=True   <br/> |Désactivez les paramètres avec Teams. Reportez-vous à cet article de l’assistance. https://answers.microsoft.com/en-us/msoffice/forum/msoffice_o365admin-mso_teams-mso_o365b/how-to-enable-or-disable-connectors-in-office-365/33d4b2c1-00eb-420a-ad83-01a2b42ad098    <br/> |21/06/17  <br/> |

## <a name="apps"></a>Applications

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L’[accès conditionnel](https://docs.microsoft.com/fr-FR/azure/active-directory/conditional-access/overview) peut ne pas fonctionner lors de l’utilisation de l’onglet « Site web » dans l’application de bureau.<br/> |Si un site web, tel qu’un portail intranet, est doté de stratégies d’accès conditionnel (par exemple, des restrictions d’adresse IP ou de navigateur), le site web peut ne pas s’afficher sous forme d’onglet dans Teams dans l’application de bureau. <br/> |Utilisez Teams dans un navigateur plutôt que dans l’application de bureau.  <br/> |01/07/18  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les options de connecteur ne sont pas disponibles pour certaines équipes  <br/> |Lorsque vous cliquez avec le bouton droit sur un canal, l'option Connecteurs ne s'affiche pour aucun membre de l'équipe.  <br/> |Le créateur de l'équipe doit posséder une boîte aux lettres en ligne. Sinon, l'option Connecteur n'est pas disponible. Il s'agit d'un comportement normal.  <br/> |26/06/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L’application « Affectations » reste visible lorsqu’elle est désactivée  <br/> |Lorsque l’application « Affectations » est désactivée dans le centre d’administration, elle reste visible au sein du client Teams pour les utilisateurs disposant d'une licence EDU. Si elle est sélectionnée lorsqu’elle est désactivée, le message d’erreur suivant s’affiche : « Oh ! Une erreur s’est produite... »  <br/> |Aucune solution.  <br/> |29/12/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de supprimer les connecteur en tant que propriétaire d’équipe  <br/> |Si vous essayez de supprimer un connecteur en tant que propriétaire, alors que vous pouvez ajouter un connecteur, lorsque l’option « Autoriser les membres à créer, mettre à jour et supprimer des connecteurs » est désactivée, une erreur indiquant que l’utilisateur n'est pas autorisé à effectuer cette action est déclenchée. <br/> |Pour autoriser le propriétaire à supprimer le connecteur, activez temporairement l’option « Autoriser les membres à créer, mettre à jour et supprimer des connecteurs ».  <br/> |27/07/2018  <br/> |

## <a name="audio-conferencing"></a>Audioconférence,

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les appelants RTC ayant le même numéro « De » sont affichés comme le même utilisateur dans la liste de présence de la réunion.  <br/> |Lorsque plusieurs appelants RTC rejoignent une réunion et que leurs identifications de l’appelant sont masquées sous la forme d'un numéro unique, ils s'affichent en tant qu'appelant unique dans la liste de présence de la réunion.  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|Le panneau d'information sur la réunion ne s'affiche pas de façon intermittente.  <br/> |Le panneau d'informations de réunion peut ne pas s'afficher dans le client Teams, lorsque les utilisateurs tentent de rechercher les numéros de téléphone du pont de conférence ou l'ID de conférence.  <br/> |Consultez les détails de la réunion ou le calendrier Outlook pour afficher les numéros de téléphone du pont de conférence ou l'ID de la conférence.  <br/> |25/09/2017  <br/> |
|Les invitations à des réunions à partir du complément Outlook affichent des caractères anormaux dans les coordonnées RTC pour les paramètres régionaux non américains.  <br/> |Lors de la planification de réunions privées à l'aide du complément Outlook pour Microsoft Teams sur un ordinateur avec des paramètres régionaux non américains, les coordonnées RTC peuvent contenir des caractères anormaux.  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|La sortie de numérotation doit utiliser 5 chiffres ou plus.  <br/> |Les utilisateurs qui tentent de composer un numéro à partir d'une réunion doivent taper 5 chiffres ou plus, même si la règle de normalisation du forfait de numérotation est disponible pour normaliser la numérotation des numéros courts à E.164.  <br/> |Appelez en tapant le numéro SDA complet ou le format de numéro local, au lieu du numéro de poste interne.  <br/> |25/09/2017  <br/> |
|Le contrôle d'appel sortant ne s'affiche pas de façon intermittente.  <br/> |Le contrôle d'appel sortant peut ne pas être visible à partir du panneau Informations sur la réunion.  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|L'ID de conférence statique n'est pas pris en charge pour les réunions Microsoft Teams.  <br/> |Si l'administrateur remplace le paramètre par défaut de l'ID de conférence dynamique par l'ID de conférence statique, ce paramètre ne s'applique pas aux réunions Microsoft Teams. Reportez-vous à la rubrique [Utiliser des ID dynamiques d’audioconférence dans votre organisation](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|Les coordonnées de réunion RTC ne sont pas disponibles pour les utilisateurs locaux de Skype Entreprise.  <br/> |Si l'utilisateur est un utilisateur local de Skype Entreprise, à qui on a attribué Skype Entreprise Online, une audioconférence et des licences Teams, toutes les réunions programmées à l'aide de Teams n'incluront pas les coordonnées de réunion RTC. <br/> |Aucune solution.  <br/> |1/2/2018  <br/> |

## <a name="authentication"></a>Authentification

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lorsque vous tentez d'ouvrir Teams sur Internet Explorer ou Edge, une boucle se produit ou le programme se bloque et ne se connecte pas.   <br/> | Votre organisation utilises la fonction de sites approuvés dans Internet Explorer et l'application Web Teams n'est pas correctement journalisée car les sites approuvés pour Teams ne sont pas autorisés. <br/>|Dans les paramètres d'IE, effectuez les modifications suivantes en utilisant des droits d'administrateur ou un objet de stratégie de groupe :<br/><ol><li>Sous **Options Internet** &gt; **Confidentialité** &gt; **Avancé**, acceptez les cookies internes et tierce partie et cochez la case **Toujours autoriser les cookies de la session**.</li><li>Cliquez sur **Options Internet** &gt; **Sécurité** &gt; **Sites de confiance** &gt; **Sites** et ajoutez l’adresse suivante :<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>REMARQUE</b> : Validez et autorisez toujours les URL approuvées pour Teams et les conditions requises figurant dans le document suivant : [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Restrictions du complément Outlook  <br/> |Pour utiliser le complément Outlook, vous devez vous connecter à Teams au moyen de l'authentification multifacteur (MFA). Si la MFA échoue au cours de la procédure de connexion, vous pourrez toujours vous connecter à Teams, mais un message d'erreur s'affichera lorsque vous essayerez d'utiliser le complément.  <br/> Pour l'instant, le complément est uniquement disponible pour les utilisateurs Windows.  <br/> Le complément ne fonctionnera pas si vous utilisez une authentification par proxy.  <br/> | Aucune solution. <br/> |02/08/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams se connectera toujours au compte de l’ordinateur lié à un domaine.   <br/> |Si un utilisateur qui a deux comptes Teams différents et une machine avec la jonction à un domaine activée, Teams utilisera le profil lié à un domaine pour connecter automatiquement l’utilisateur à Teams. Pour basculer sur l’autre compte Teams, l’utilisateur doit se déconnecter manuellement de l’application puis entrer les informations d'identification du second compte pour se connecter. S’il se déconnecte de Teams et redémarre la machine, au démarrage, Teams se connectera automatiquement en utilisant le profil joint au domaine. <br/> | Aucune solution. <br/> |02/08/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Échec de l’authentification moderne - Authentification par formulaire désactivée  <br/> |Si l'authentification multifacteur échoue, réalisez l'authentification depuis l'application web.  <br/> Pour plus d'informations, voir [Prise en charge du paramètre des services ADFS prompt=login](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Vérifiez ce paramètre : `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19/06/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Planificateur sur la version d’authentification unique (SSO) <br/> |L'authentification unique (SSO) ne s'applique pas au planificateur. Vous devrez vous reconnecter à la première utilisation du planificateur sur chaque client.  <br/> |Aucune solution. Nous travaillons actuellement sur d'autres améliorations du système d'authentification.  <br/> |28/02/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible d'enregistrer la photo de profil  <br/> |Les utilisateurs ne peuvent pas enregistrer leur photo de profil lorsque la boîte aux lettres Exchange est hébergée sur site sur Exchange 2016 CU2 ou une version inférieure.  <br/> |Aucune solution.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Navigateur

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Artéfacts verts dans le rendu vidéo Chrome  <br/> |Des artéfacts verts apparaissent lors du visionnement d'une vidéo ou du partage de l'écran dans un appel ou une réunion dans Chrome.  <br/> |Désactivez le paramètre d'accélération matérielle dans Chrome.  <br/> |03/08/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Prise en charge du client web par Safari  <br/> | Les équipes sont désormais disponibles en mode aperçu sur Safari 11.1 + sur macOS. En mode Aperçu, les utilisateurs peuvent exécuter dans les problèmes liés à la prévention de suivi Safari Intelligent[Problèmes connus Safari](https://go.microsoft.com/fwlink/?linkid=2062082).  <br/> | Tandis que le support des navigateurs Safari est en version préliminaire, accédez à **Préférences > Confidentialité**  et décochez la case du paramètre **Empêcher le suivi intersites**  . Ensuite, fermez votre navigateur et accédez à l’adresse teams.microsoft.com dans Safari. <br/> |02/11/2016  <br/> |


## <a name="channels"></a>Canaux

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lorsqu'un utilisateur quitte l’entreprise, il apparaît dans Microsoft Teams comme « Utilisateur inconnu »<br/> |Lorsqu'un utilisateur quitte l’entreprise, il apparaît dans Microsoft Teams comme « Utilisateur inconnu ». L'onglet de conversation affiche également : « Un utilisateur inconnu a été ajouté à l’équipe ». <br/> |Aucune solution.  <br/> |12/09/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs ne peuvent pas recréer un nom de canal préexistant.  <br/> |Une fois qu'un nom de canal a été défini, même si le canal est supprimé, le nom ne peut pas être réutilisé. Notre système conserve ces données pour des raisons de protection des informations.  <br/> |Aucune solution.  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Renommer un canal dans Microsoft Teams ne renomme pas le dossier correspondant dans SharePoint Online.  <br/> |Si un canal est renommé dans Microsoft Teams, le dossier dans la bibliothèque de documents SharePoint Online correspondant à l’équipe ne reflète pas la modification. Le nom du dossier SharePoint Online apparaît en haut de l’onglet Fichiers du canal renommé.  <br/> |Aucune solution.  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L’aperçu de l’URL peut ne pas s’afficher pour toutes les URL  <br/> |Certaines URL peuvent ne pas afficher d’aperçu.  Cela dépend de la capacité d’afficher un aperçu de l’URL d’origine. <br/> |Aucune solution. <br/> |01/09/2018 <br/> |

## <a name="chat"></a>Conversation

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les @mentions de message supprimé envoient une notification avec le lien du canal  <br/> |Il existe une restriction connue lorsque vous êtes @mentionné dans un message qui est supprimé ; la notification dans le flux accédera au canal mais pas au message spécifique. <br/> | Par défaut <br/> | 28/03/2017  <br/>|


## <a name="client"></a>Client



|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de démarrer Teams pour Surface Hub à partir du Microsoft Store |Microsoft Teams pour Surface Hub ne démarre pas lorsque vous cliquez sur **Lancer** dans le Microsoft Store. | Le lancement de Teams pour l’application Surface Hub à partir de la liste du Microsoft Store n’est pas pris en charge par Windows sur Surface Hub. <br> <br/> Redémarrez le Surface Hub après l’installation de Teams. | 27/02/18 |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Teams ne se met pas à jour automatiquement   <br/> | Lorsque Microsoft Teams est installé dans Program Files à l’aide des scripts d'installation au lieu de l’emplacement par défaut, le client ne se met pas à jour automatiquement lorsque de nouvelles versions sont disponibles.    <br/> | Par défaut. Assurez-vous d'installer l’application dans l’emplacement par défaut : `user\Appdata`.  <br/> | 07/09/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Un lien symbolique ou le mappage d’un lecteur sur C:\utilisateurs lance l’application sur un écran blanc  <br/> | Lorsque Microsoft Teams est installé dans Program Files à l’aide des scripts d'installation au lieu de l’emplacement par défaut, le client ne se met pas à jour automatiquement lorsque de nouvelles versions sont disponibles.   <br/> | Par défaut. Assurez-vous d'installer l’application dans l’emplacement par défaut : `user\Appdata`. Si le mappage doit exister, vous devez utiliser la version web de Microsoft Teams.  <br/> | 07/09/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Un lien symbolique ou le mappage d’un lecteur sur C:\utilisateurs lance l’application sur un écran blanc  <br/> |Si l’emplacement par défaut de `C:\users\<user>\appData` est modifié en déplaçant le dossier `C:\users` ou en utilisant un lien symbolique, l’application se lance avec un écran blanc.   <br/> |Il n’existe pas de solution de contournement. Si le mappage doit exister, vous devez utiliser la version web de Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Environnement

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L'archivage des boîtes aux lettres de groupe (stockage supplémentaire) n'est pas activé.  <br/> |Dans le Centre de sécurité et conformité Office 365, les administrateurs généraux n'ont pas la possibilité d'activer l'archivage pour les boîtes aux lettres de groupe. Cela est possible uniquement pour les boîtes aux lettres utilisateur.  <br/> |Si la capacité de la boîte aux lettres de groupe est presque atteinte, prenez contact avec le support de Microsoft Office pour augmenter la capacité.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Accès invité

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les clients des pays de l'UE et de la région APAC reçoivent une erreur lorsqu'ils ajoutent un utilisateur invité à partir d'un autre client.    <br/> | Les clients des pays de l'UE et de la région APAC subissent un retard de réplication entre Microsoft Teams et Azure Active Directory. Lorsqu'un utilisateur d'un client d'un pays de l'UE ou de la région APAC tente d'ajouter un utilisateur invité d'un autre client, il reçoit un message d'erreur indiquant de réessayer.   <br/> |Cliquez sur le bouton Réessayer pour ajouter l'utilisateur invité.  <br/> |08/11/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Wiki non créé pour les canaux créés par les invités  <br/> |Lorsqu'un invité crée un nouveau canal, l'onglet **Wiki** n'est pas créé. Il n'existe pas de méthode pour joindre manuellement un onglet **Wiki** au canal. <br/> |Aucune solution.  <br/> |20/09/2017  <br/>|

## <a name="meetings"></a>Réunions

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs ne peuvent pas accéder aux réunions/connecteurs mais ont des boîtes aux lettres Exchange Online. <br/> |Le client bloque activement EWS des services dans Exchange Online mais MS Teams doit être compatible au sein des stratégies EWS. <br/> |Pour que MS Teams soit compatible, vous devez ajouter les chaînes de l’agent utilisateur suivantes pour MS Teams dans EWSAllowList : `SkypeSpaces/*` et `MicrosoftNinja/*`, astérisques inclus. La commande suivante peut être utilisée : `Set-organizationconfig -EwsAllowList @{Add="MicrosoftNinja/*","SkypeSpaces/*"}`<br/> Pour plus d'informations : https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps. <br/> |30/05/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise est requis pour certaines réunions.  <br/> |Votre calendrier de rendez-vous s'affiche de manière pratique dans Microsoft Teams. Pour participer à une réunion, cliquez sur le bouton **Rejoindre**. <br/> Nous poursuivons le développement à ce sujet, mais pour le moment, si la réunion était planifiée au moyen de Skype Entreprise et que vous cliquez sur **Rejoindre**, Microsoft Teams lance votre client Skype Entreprise pour finaliser votre accès à la réunion. Les réunions planifiées dans Microsoft Teams s'ouvrent directement dans le produit.  <br/> À l'avenir, nous uniformiserons cette procédure.  <br/> |Cliquez sur **Rejoindre**. Microsoft Teams décidera judicieusement si Skype Entreprise est requis pour qu'un utilisateur rejoigne la réunion en fonction de l'URL mentionnée dans la description de la réunion.  <br/> |13/03/2017  <br/> |


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Nombre maximum de participants pour les réunions  <br/> |Chaque réunion Microsoft Teams peut accueillir jusqu'à 250 participants.  <br/> |Créer des événements en direct dans teams qui peuvent accueillir 10 000 utilisateurs.  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Réunions non disponibles  <br/> |La fonctionnalité de réunion n’est pas disponible lorsque la boîte aux lettres Exchange est hébergée sur site dans une version inférieure à Exchange 2016 CU3.  <br/> |Effectuez une mise à niveau vers Exchange 2016 CU3 ou une version suivante pour le déploiement sur site.  <br/> |28/02/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Aucun son lors du partage de contenu pendant une réunion de diffusion  <br/> |Lors du partage de contenu pendant une réunion de diffusion, le son du contenu partagé (lien youtube ou fichier vidéo enregistré) ne peut pas être entendu par les participants.  <br/> |Il ne s’agit pas d'un comportement par défaut.  Teams ne prend pas en charge actuellement le son du contenu partagé  <br/> |09/10/2018  <br/> |

## <a name="mobile"></a>Mobile

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de voir les canaux ajoutés automatiquement aux favoris  <br/> |Certains membres ne peuvent pas voir les canaux ajoutés automatiquement aux favoris sur l’application mobile.  <br/> |Pour afficher les canaux ajoutés automatiquement aux favoris sur leur application mobile, les membres doivent se connecter au préalable l’application de bureau ou web.  <br/> |30/04/2018  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Il est possible que les utilisateurs ne puissent pas changer de compte sur les appareils mobiles gérés par Intune  <br/> |Il est possible que les utilisateurs ne puissent pas changer de compte sur les appareils mobiles gérés par Intune.  <br/> |Aucune solution.  <br/> |20/09/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Différences de disposition des équipes sur le client mobile  <br/> |Les équipes s'affichent dans l'ordre alphabétique et les canaux ne peuvent pas être réduits sur le client mobile.  <br/> |Aucune solution.  <br/> |13/03/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Problèmes que vous pouvez rencontrer si vous utilisez iOS 13 bêta  <br/> |1. les notifications Teams ne sont pas activées.  Cela inclut les conversations, les mentions et les appels.  2. L’aperçu des fichiers ne fonctionne pas avec la version bêta.  <br/> |Il n'existe actuellement aucune solution.  Nous travaillons en collaboration avec les développeurs d’Apple pour trouver des correctifs pour ces problèmes.  <br/> | 25/6/19  <br/>|


## <a name="people"></a>Personnes

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Photos de profil des utilisateurs  <br/> | Teams ne comporte pas actuellement de mécanisme permettant d’empêcher les utilisateurs de changer leur photo. L’équipe BTS a rencontré l’équipe de développement qui a consigné le point suivant à prendre en considération : Fonctionnalité 108874 : stratégie IT pour désactiver le chargement de photos de profil   <br/> | Si vous avez des clients qui souhaiteraient avoir la possibilité d’empêcher le chargement de photos de profil dans Teams, veuillez ajouter leur vote et leur script commercial aux commentaires ici : https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01/03/2017 <br/> |



## <a name="phone-system"></a>Système téléphonique

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Service de compte de ressource mal configuré <br/> |Les comptes de ressource associés à un standard automatique ou à une file d’attente d’appels créée avant le mois de janvier 2019 risquent de ne pas avoir le paramètre Department correctement défini, ce qui peut entraîner l’échec d’une affectation de numéro de téléphone. Un correctif est en cours de préparation pour résoudre ce problème. <br/><br/> Le paramètre Department (service) des comptes de ressources configurés à l’aide de New-CsHybridApplicationEndpoint avec Skype Entreprise Server n’est pas correctement configuré, ce qui entraîne l’échec de la création de comptes de ressources dans Skype Entreprise en ligne. Dans ce cas, vous devez configurer le nom du service dans Active Directory avant de le synchroniser en ligne.|Pour résoudre ce problème, vous pouvez exécuter la cmdlet suivante afin de définir le paramètre Department. Set-MsolUser -ObjectId <Resource Account Object ID> -Department "Instance d’application de communication Microsoft" <br/> |8/5/19 <br/> |



|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Retard de synchronisation des comptes de ressource|Impossible d’attribuer un numéro de téléphone au compte de ressources ou affichage du message d’erreur « L’instance d’application suivante n’est pas présente dans BVD ».|Patientez 24 heures pour la synchronisation. Si 24 heures se sont déjà écoulées, supprimez l’affectation du numéro de téléphone, supprimez le compte de ressource, puis recréez-en un sous un autre nom.|18/05/2018|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible d’attribuer numéro de service payant à partir du centre d’administration Teams|Lorsque vous essayez d’attribuer un numéro de service payant dans le centre d’administration Teams, l’erreur « Vous avez besoin d’une licence de système téléphonique » s’affiche.|Utilisez plutôt des cmdlets PowerShell pour attribuer un numéro de service payant.|18/05/2018|


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Compte de ressource endommagé|Compte de ressources non fonctionnel|La suppression ou le remplacement de la licence d’un compte de ressource ou la création d’un compte de ressource avec la même URI SIP qu’un compte supprimé précédemment endommage le compte de ressource.|18/05/2018|


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Numéro de téléphone bloqué|Numéro de téléphone bloqué : la suppression du compte de la ressource avant de supprimer le numéro de téléphone bloque le numéro de téléphone.|Contactez le service clientèle Microsoft pour libérer le numéro de téléphone.|18/05/2018|


## <a name="provisioning"></a>Mise en service

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Utilisateur SharePoint incorrect créé pour le site SharePoint de Microsoft Teams  <br/> |Le créateur SharePoint d'un groupe Microsoft Teams est un administrateur SharePoint, pas l'utilisateur correct.  <br/> Lors d'un audit depuis la console d'administration SharePoint, le créateur de la page de collection de sites associé au groupe Office 365 créé pour l'équipe dans Microsoft Teams est l'administrateur SharePoint.  <br/> |Aucune solution.  <br/> |21/07/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs n'arrivent pas à créer une équipe.  <br/> |Votre entreprise peut avoir défini une politique limitant les personnes qui peuvent créer des groupes ou des équipes Office 365.  <br/> |Consultez votre administrateur informatique pour comprendre la politique de votre entreprise en matière de création de groupes et d'équipes.  <br/> |13/03/2017  <br/> |

## <a name="skype-for-business-to-teams-upgrade"></a>Mise à niveau de Skype Entreprise vers Microsoft Teams

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|

## <a name="tabs"></a>Onglets

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Onglet de site web source de confusion pour les clients  <br/> |Les onglets de site web ne sont pas équivalents à votre navigateur. Un certain nombre de sites, particulièrement ceux qui requièrent une authentification ou l’utilisation de fenêtres contextuelles, ne fonctionneront pas s’ils sont épinglés en tant qu’onglet de site web.  <br/> |Nous nous efforçons d’améliorer l’interface utilisateur pour que cela soit plus clair pour les clients.  <br/> |02/05/2018  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Onglets qui ne fonctionnent pas depuis l’accès conditionnel a été activé <br/> |Certains onglets peuvent ne plus se charger dans le client de bureau depuis que l’accès conditionnel a été activé sur le client. Les onglets se chargent lorsque le client web est utilisé. Certains onglets pouvant être affectés sont les suivants : PowerBI, VSTS, PowerApps et liste SharePoint.  <br/> |Pour afficher les onglets concernés, vous devez utiliser Teams dans Microsoft Edge, IE ou Chrome avec l’extension de comptes Windows 10 installée. Certains onglets dépendent toujours de l’authentification web, qui ne fonctionne pas dans le client de bureau lorsqu’une autorité de certification est activée. Nous travaillons avec des partenaires pour activer ces scénarios ; nous avons activé jusqu’à présent le Planificateur, OneNote et Stream. <br/> |05/04/2018  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La liste des espaces de travail n'est pas triée par ordre alphabétique.  <br/> |Les utilisateurs qui passent d'un espace de travail à un autre lors de l'ajout d'un onglet PowerBI sont invités à choisir celui qu'ils souhaitent activer parmi une liste non classée par ordre alphabétique.  <br/> |Aucune solution.  <br/> |13/03/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La barre de défilement disparaît quand des rapports sont sélectionnés.  <br/> |Les utilisateurs qui ajoutent des rapports PowerBI ne peuvent pas faire défiler une liste plus longue que la taille d'un écran de rapports sans perdre leur barre de défilement.  <br/> |Utilisez les flèches vers le haut et vers le bas pour faire défiler la liste.  <br/> |13/03/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Intégration du Planificateur Teams avec le Planificateur en ligne <br/> |Les paquets de tâches dans le Planificateur ne s’affichent pas dans l’expérience en ligne du Planificateur.  <br/> |Aucune solution. <br/> |28/02/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Onglet OneNote existant  <br/> |Les onglets OneNote existants créés lors de la préversion publique de Microsoft Teams ne peuvent pas être renommés ni supprimés.  <br/> |Aucune solution. <br/> |08/11/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Fonction recherche dans l’onglet liste SharePoint  <br/> |Essayer d’ouvrir un fichier à partir de la fonction recherche de l’onglet liste SharePoint fait afficher une invite « Vous avez besoin d’une nouvelle application pour ouvrir ce fichier » et le fichier ne sera pas ouvert. <br/> |Ouvrir directement à partir de liste plutôt que de la barre de recherche. <br/> |11/2/2019  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Échec du téléchargement d’un fichier <br/> |Toute tentative de téléchargement d’un fichier lorsque le chemin d’accès à un fichier contient une apostrophe se solde en un échec avec affichage du message «Le fichier n’a pas été téléchargé» lors de l’utilisation du client de bureau Microsoft Teams. <br/> |Téléchargez le fichier à partir du client Web ou de SharePoint Online <br/> |10/5/2019  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de charger ou de télécharger un fichier OneNote <br/> |La tentative de chargement ou de téléchargement d’un fichier ou d’un bloc-notes OneNote échouera en utilisant Microsoft Teams. <br/> |Charger ou télécharger le fichier directement dans SharePoint Online <br/> |7/5/2019  <br/> |

## <a name="teams"></a>Équipes

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les journaux d’audit peuvent indiquer un nom d’utilisateur incorrect comme initiateur lorsqu’une personne a été supprimée de Teams  <br/> |Une équipe Teams est un groupe moderne dans AAD. Lorsque vous ajoutez/supprimez un membre par l’intermédiaire de l'interface utilisateur de Teams, le flux sait exactement quel utilisateur a initialisé la modification, et le journal d’audit reflète les informations correctes. Cependant, si un utilisateur ajoute ou supprime un membre via AAD, la modification est synchronisée sur le serveur principal de Teams sans indiquer à Teams qui a initialisé l’action. Microsoft Teams sélectionne le premier propriétaire de Teams comme initiateur, ce qui est finalement répercuté dans le journal d’audit également.    <br/> |  <br/> |11/05/2018  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Le chargement de photos dans Teams n'est pas bloqué dans OWA/Outlook comme le requiert la stratégie   <br/> | Teams permet aux utilisateurs de charger des photos directement dans Office 365, en dépit des paramètres de stratégie définis pour empêcher cette action dans OWA.   <br/> |<br/>  |16/10/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La liste d'équipes publiques n'affiche pas toutes les équipes  <br/> |La liste des équipes publiques repose sur Microsoft Graph.  <br/> |Si une équipe n'est pas affichée, essayez de la rechercher au moyen du champ de recherche situé dans le coin supérieur droit. Les propriétaires d’équipe doivent en outre communiquer les noms des équipes à leurs collègues, plusieurs équipes peuvent s’afficher dans les résultats de recherche. <br/> | 21/07/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les noms d’équipes contenant des caractères spéciaux peuvent créer des erreurs lors de la création de réunions  <br/> |L’utilisateur recevra le message **Une erreur s’est produite** en rouge s’il tente de créer une réunion pour une équipe dont le nom contient des caractères spéciaux.   <br/> |Renommez ou créez à nouveau l’équipe avec un nom qui ne contient pas le caractère « / ».  <br/> |13/07/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Un nom d'équipe contenant un symbole &amp; interrompt la fonctionnalité du connecteur  <br/> |Lorsqu'un nom d'équipe est créé avec le symbole &amp;, les connecteurs de l'équipe ou du groupe ne peuvent pas être établis.  <br/> |N'utilisez pas de caractères spéciaux dans le nom des équipes.  <br/> |21/06/17  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Maximum de 5000 membres par équipe  <br/> |Chaque équipe Microsoft Team peut accueillir un maximum de 5000 membres.  <br/> |Aucune solution.  <br/> |6/2/2019  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La suppression d'une équipe supprime également le groupe associé à celle-ci  <br/> |Il est possible que les utilisateurs ne réalisent pas que le groupe Office 365 sous-jacent est supprimé lorsque l'équipe est supprimée. En outre, si le groupe Office 365 sous-jacent est supprimé, l'équipe l'est également.  <br/> |Les langues supplémentaire dans Microsoft Teams fournissent cette information à l'utilisateur. Cette information n'est pas disponible dans l'interface Groupes Office 365. Votre service d’assistance peut récupérer un groupe ou une équipe supprimé(e).  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Application de bureau Teams affichant un écran blanc  <br/> | <br/> |Essayez de supprimer ou de réinstaller les pilotes graphiques sur l’ordinateur, ou démarrez Teams depuis une ligne de commande avec un indicateur de désactivation du GPU :<ul><li>Pour Windows : ouvrez l'invite de commande et entrez la commande suivante : `cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Pour Mac : démarrez le Terminal et entrez la commande suivante : `cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L’utilisateur ne reçoit pas d’e-mail de bienvenue lorsqu’il est ajouté par l’administrateur.  <br/> |Lors de l’ajout d’un membre à une équipe à l’aide de PowerShell ou du centre d’administration Teams, le membre ne reçoit pas d’e-mail de bienvenue de Microsoft Teams.  <br/> |L’ajout d’un membre directement à partir de l’interface utilisateur de Teams entraîne l’envoi d’un e-mail. Actuellement, il n’existe aucun contournement permettant de réaliser cette action via l’administration.  <br/> |12/02/19  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de déplacer, supprimer ou renommer des fichiers après modification  <br/> |Une fois qu’un fichier est modifié dans Teams, il ne peut pas être déplacé, renommé ou supprimé immédiatement <br/> |Il s’agit d’un problème connu. La solution de contournement consiste à patienter un certain temps avant d’apporter des modifications d’administration.  <br/> |12/03/19  <br/> |
