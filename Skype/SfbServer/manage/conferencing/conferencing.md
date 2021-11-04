---
title: Gérer les conférences dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Résumé : Découvrez comment gérer les conférences dans Skype Entreprise Server.'
ms.openlocfilehash: ef1afdecaec5ae237020b1681d95b556a37e2ab8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751773"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Gérer les conférences dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les conférences dans Skype Entreprise Server.
  
Cette rubrique décrit comment gérer les conférences. Pour plus d’informations sur la façon de planifier et de déployer des conférences, voir [Plan for conferencing in Skype Entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype Entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Dans Skype Entreprise Server, vous gérez les détails des conférences en spécifiant les paramètres de configuration et de stratégie comme suit. Notez que les termes conférence et réunion sont parfois utilisés indifféremment. Toutefois, en règle générale, vous pouvez penser à une réunion comme une instance spécifique de conférence.
  
- Les **paramètres** de stratégie de conférence englobent un large éventail d’options de planification et de participation, allant du fait qu’une réunion peut inclure du son et de la vidéo IP ou le nombre maximal de personnes pouvant y participer. Vous pouvez utiliser des stratégies de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.
    
    Notez que les stratégies de conférence sont appliquées à l’utilisateur ou au site et ne peuvent pas être appliquées à une réunion spécifique. Par conséquent, l’invitation à la réunion peut être créée quelques semaines à l’avance, mais la stratégie de conférence restrictive doit être appliquée au compte Skype Entreprise de l’organisateur de la réunion juste avant le début de la conférence. 
    
    Si un compte dédié est utilisé pour le rôle Organisateur de réunion, la stratégie de conférence peut rester affectée à ce compte. Si l’organisateur de la réunion utilise un compte Skype Entreprise général, la stratégie doit être supprimée une fois la conférence terminée.
    
- Les **paramètres** de configuration de réunion déterminent le type de réunion que les utilisateurs peuvent créer, en plus de contrôler comment (ou même si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent participer à ces réunions. Notez que ces paramètres affectent uniquement les réunions prévues. Les configurations de réunion sont appliquées par pool, par site ou globalement.
    
- **Les paramètres de configuration** de conférence déterminent des éléments tels que la taille maximale autorisée pour le contenu et les handouts de réunion . quantité maximale de bande passante pour le service de conférence de partage d’application ; limites de stockage et périodes d’expiration ; URL pour les téléchargements internes et externes du client pris en charge ; pointeurs vers des URL internes et externes où les utilisateurs peuvent obtenir de l’aide et des ressources de conférence ; et les ports utilisés pour le partage d’application, l’audio client, les transferts de fichiers et le trafic multimédia.
    
    Ces paramètres vous permettent de gérer les serveurs eux-mêmes. Ces paramètres ne peuvent être définies qu’à l’aide Skype Entreprise Server Management Shell. 
    
- **Les paramètres d’accès à la** connexion vous permettent de définir des informations sur la façon dont les utilisateurs appellent un numéro à partir d’un téléphone. Vous spécifiez certaines des informations d’accès à la conférence, telles que le numéro d’accès, à partir de l’onglet Conférence du Panneau de contrôle et certaines informations de numérotation,telles que le plan de numérotation, la stratégie de voix, l’itinéraire et l’utilisation PSTN, à partir de l’onglet Routage des voix du Panneau de contrôle.
    
- **Les paramètres de stratégie de code** confidentiel vous permettent de nommer et de définir le code confidentiel que les participants utilisent pour l’accès à la connexion.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gérer les conférences à l’aide Skype Entreprise Server panneau de Skype Entreprise Server Management Shell

Vous pouvez gérer la plupart des stratégies de conférence et des paramètres de configuration à l’aide du Panneau de configuration Skype Entreprise Server ou de Skype Entreprise Server Management Shell. Certains paramètres de configuration sont disponibles uniquement à l’aide Skype Entreprise Server Management Shell.
  
- Pour gérer les paramètres de stratégie de conférence :
    
  - Dans le Panneau de contrôle, sélectionnez **Conférence | Stratégie de conférence.**
    
  - Dans PowerShell, recherchez les cmdlets **-CsConferencingPolicy.**
    
- Pour gérer les paramètres de configuration de réunion :
    
  - Dans le Panneau de contrôle, sélectionnez **Conférence | Configuration de la réunion.**
    
  - Dans Skype Entreprise Server Management Shell, recherchez les cmdlets **-CsMeetingConfiguration.**
    
- Pour gérer les paramètres de numéro d’accès à la connexion :
    
  - Dans le Panneau de contrôle, sélectionnez **Conférence | Numéro d’accès à la connexion.**
    
  - Dans Skype Entreprise Server Management Shell, recherchez les cmdlets **-CsDialInConferencing.**
    
- Pour gérer les informations d’accès aux appels, telles que le plan de numérotation, la stratégie de voix, l’itinéraire et l’utilisation PSTN : 
    
  - Dans le Panneau de contrôle, sélectionnez **Conférence | Routage des voix.**
    
  - Dans Skype Entreprise Server Management Shell, recherchez les cmdlets **-CsDialPlan** et **-CsVoice.**
    
- Pour gérer les paramètres de stratégie de code confidentiel :
    
  - Dans le Panneau de contrôle, sélectionnez **Conférence | Stratégie de code confidentiel**.
    
  - Dans Skype Entreprise Server Management Shell, recherchez les cmdlets **-CsPinPolicy.**
    
- Pour gérer les paramètres de configuration de conférence, vous devez utiliser Skype Entreprise Server Management Shell. Recherchez **les cmdlets -CsConferencingConfiguration.**
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype Entreprise Server Cmdlets Management Shell

Vous pouvez utiliser les cmdlets Skype Entreprise Server Management Shell suivantes pour gérer les conférences : 
  
**Paramètres de stratégie de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies de conférence qui ont été configurées pour être utilisées dans votre organisation. Les stratégies de conférences déterminent les fonctionnalités pouvant être utilisées au cours des conférences ; elles indiquent par exemple si la conférence peut inclure de l’audio et de la vidéo sur IP ou encore le nombre maximal de participants à une réunion.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Affecte une stratégie de conférence au niveau de l’étendue Utilisateur.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crée une stratégie de conférence à utiliser dans votre organisation.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Supprime la stratégie de conférence spécifiée.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifie une stratégie de conférence existante.  <br/> |
   
**Paramètres de configuration des réunions**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retourne des informations sur les paramètres de configuration de réunion actuellement utilisés dans votre organisation. Les paramètres de configuration de réunion déterminent le type de réunion que les utilisateurs peuvent créer et contrôlent la façon dont les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent participer à ces réunions.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de réunion au niveau de l’étendue Site ou Service. Notez que ces paramètres affectent uniquement les réunions prévues ; elles n’affectent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans Skype Entreprise.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Supprime une collection existante de paramètres de configuration de réunion.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifie les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
   
**Paramètres de configuration de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retourne des informations sur les paramètres de configuration de conférence de votre organisation. Les paramètres de conférence déterminent certains éléments comme la taille maximale autorisée des documents et du contenu de la conférence, la période de grâce du contenu (à savoir, la durée pendant laquelle le contenu sera stocké avant d’être supprimé) et les URL des téléchargements internes et externes du client pris en charge.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de conférence.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Supprime la collection spécifiée de paramètres de configuration de conférence.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifie une collection existante de paramètres de configuration de conférence.  <br/> |
   
**Paramètres de configuration de la connexion**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Retourne des informations sur les annuaires de conférences configurés pour être utilisés dans votre organisation. Les annuaires des conférences permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Récupère des informations sur la façon dont Skype Entreprise Server répond lorsque des utilisateurs rejoignent ou quittent une conférence téléphonique.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retourne des informations sur tous les numéros d’accès aux conférences téléphoniques configurés pour être utilisés dans votre organisation.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Retourne les paramètres de signalisation DTMF (Dual-Tone Multifrequency ou numérotation en fréquences vocales) utilisés pour la conférence rendez-vous. Le système DTMF permet aux utilisateurs qui rejoignent une conférence d’en contrôler les paramètres (comme la capacité de mettre en sourdine ou de verrouiller ou déverrouiller la conférence) à l’aide du clavier du téléphone.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Renvoie une liste de langues, y compris les langues régionales/étrangères, pris en charge pour une Skype Entreprise Server conférences téléphoniques. Ces langues sont utilisées pour relayer les messages audio et les instructions aux utilisateurs participant à la conférence grâce à un numéro de téléphone.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retourne des informations sur les plans de numérotation utilisés au sein de votre organisation.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Affecte un plan de numérotation à un ou plusieurs utilisateurs ou groupes.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importe les annuaires des conférences Microsoft Office Communications Server 2007 R2 vers Skype Entreprise Server. Cela permet d’assurer l’interopérabilité entre Skype Entreprise Server et Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Déplace un annuaire de conférence existant d’un pool vers un autre. Les annuaires de conférence permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crée un annuaire de conférence en vue de l’utiliser dans votre organisation. Les annuaires de conférence permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crée un nouveau numéro d’accès à la conférence rendez-vous.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration pour la conférence rendez-vous. Ces paramètres déterminent le Skype Entreprise Server réponse des utilisateurs qui rejoignent ou quittent une conférence téléphonique. Sont retournées en particulier les informations qui indiquent si les participants sont tenus ou non d’enregistrer leur nom en rejoignant la conférence et comment (ou si) le système doit annoncer qu’une personne a rejoint la conférence ou l’a quittée.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crée un nouveau plan de numérotation.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Supprime un annuaire de conférence existant. Les annuaires de conférence permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Supprime un numéro d’accès à une conférence rendez-vous existant.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Supprime une ou plusieurs collections de paramètres de configuration de conférence rendez-vous. Ces paramètres déterminent le Skype Entreprise Server réponse des utilisateurs qui rejoignent ou quittent une conférence téléphonique.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Supprime une collection existante de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifie les valeurs de propriétés d’un numéro d’accès de conférence rendez-vous existant. La conférence rendez-vous permet aux utilisateurs d’utiliser un téléphone fixe ou mobile ou tout autre périphérique sur le réseau téléphonique public commuté pour rejoindre la partie audio d’une conférence.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifie les paramètres qui déterminent le Skype Entreprise Server lorsque les utilisateurs rejoignent ou quittent une conférence téléphonique.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifie les paramètres de signalisation DTMF (Dual Tone Multi-Frequency) de la conférence rendez-vous.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifie un plan de numérotation existant.  <br/> |
   
**Paramètres de stratégie de code confidentiel**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Retourne des informations sur les stratégies d’authentification par code confidentiel des clients configurées pour être utilisées dans votre organisation. L’authentification par code confidentiel permet aux utilisateurs d’accéder Skype Entreprise Server en fournissant un code confidentiel au lieu d’un nom d’utilisateur et d’un mot de passe.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Affecte une stratégie cliente de code confidentiel à un utilisateur ou un groupe d’utilisateurs.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crée une stratégie d’authentification par code confidentiel pour les clients.  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Supprime la stratégie de code confidentiel.  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifie une ou plusieurs stratégies de code confidentiel (PIN) client existantes.  <br/> |
   
**Autres paramètres de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Désactive une salle Skype Entreprise Server réunion. Une salle de réunion est un appareil de conférence conçu pour répondre aux besoins de conférences vidéo et de collaboration dans des petites salles de conférence. Lorsque vous désactivez un objet salle de réunion, vous supprimez tous les attributs Active Directory spécifiques Skype Entreprise Server affectés au compte d’utilisateur qui représente la salle de réunion. Toutefois, le compte d’utilisateur Active Directory proprement dit n’est pas supprimé.  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Active une salle Skype Entreprise Server réunion. Pour activer une salle de réunion, vous devez d’abord créer un compte d’utilisateur Active Directory qui représentera ce système. Notez que, même si les objets salle de réunion sont basés sur les comptes d’utilisateurs, ces objets n’apparaissent pas lorsque vous exécutez l’applet de commande Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Renvoie des informations sur la notification d’exclusion des conférences utilisée dans votre organisation. La notification d’exclusion des conférences est un message qui s’affiche pour les utilisateurs qui rejoignent la conférence à l’aide d’un lien hypertexte (par exemple, les utilisateurs qui collent un lien d’accès à la conférence dans un navigateur tel que Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Retourne des informations sur toutes les Skype Entreprise Server de réunion configurées pour être utilisés dans l’organisation.  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Déplace un objet Skype Entreprise Server salle de réunion d’un pool de bureaux d’inscriptions à un autre.  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Efface le texte de l’en-tête et du corps de la notification d’exclusion des conférences utilisée dans votre organisation. La notification d’exclusion des conférences est un message qui s’affiche pour les utilisateurs qui rejoignent la conférence à l’aide d’un lien hypertexte (par exemple, les utilisateurs qui collent un lien d’accès à la conférence dans un navigateur tel que Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifie les valeurs de propriété d’une salle Skype Entreprise Server réunion existante.  <br/> |
   
**Paramètres de test**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Teste l’aptitude de deux utilisateurs à prendre part à une conférence de partage d’application.  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Teste pour voir si un utilisateur peut se connecter à son fournisseur de services d’audioconférence. Un fournisseur de services d’audioconférence est une société tierce qui propose des services de conférence aux entreprises. Entre autres choses, les fournisseurs d’audioconférence permettent aux utilisateurs situés hors site et non connectés au réseau d’entreprise ou à Internet de participer à la partie audio d’une conférence ou d’une réunion.  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Teste l’aptitude de deux utilisateurs à prendre part à une conférence audio/vidéo (A/V).  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Vérifie si deux utilisateurs peuvent ou non participer à une conférence web Skype Entreprise Server qui inclut des activités telles que le partage ou l’affichage de PowerPoint diapositives, tableaux blancs ou sondages. L’cmdlet vérifie également que le service de conférence web Skype Entreprise Server peut découvrir Office Web Apps Server et qu’un client peut télécharger un fichier PowerPoint pour diffusion par Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Vérifie si un utilisateur peut participer à une session de conférence rendez-vous.  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Teste un numéro de téléphone par rapport à un plan de numérotation (anciennement appelé « profil d’emplacement ») et retourne la règle de normalisation qui sera appliquée au numéro, ainsi que le numéro traduit après application de la règle de normalisation.  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Teste la capacité de trois utilisateurs à participer à une conférence Skype Entreprise Server Mobility Service. Le service de mobilité permet aux utilisateurs de téléphones mobiles tels que des iPhone et Windows Phone d’échanger des messages instantanés et des informations de présence. stocker et récupérer la messagerie vocale en interne plutôt qu’avec son fournisseur sans fil ; et tirez parti Skype Entreprise Server fonctionnalités telles que l’appel via le travail et la conférence sortante.  <br/> **Remarque :** Les clients qui utilisent MCX ne sont pas pris en charge Skype Entreprise Server 2019.|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Teste la capacité d’une paire d’utilisateurs à planifier, rejoindre et mener une conférence en ligne à l’aide de l’API UCWA (Unified Communications Web API).  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Renvoie des informations de diagnostic pour les fonctionnalités de conférence de données incluses dans Skype Entreprise Server.  <br/> |
