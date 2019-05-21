---
title: Gestion des conférences dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Résumé: Découvrez comment gérer les conférences dans Skype entreprise Server.'
ms.openlocfilehash: 55fd2ff645e6e95199b2558ef494eea019b155bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280424"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Gestion des conférences dans Skype entreprise Server
 
**Résumé:** Apprenez à gérer les conférences dans Skype entreprise Server.
  
Cette rubrique indique la marche à suivre pour la gestion des conférences. Pour plus d’informations sur la planification et le déploiement de conférences, voir [planifier les conférences dans Skype entreprise Server](../../plan-your-deployment/conferencing/conferencing.md) et [déployer des conférences dans Skype entreprise Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Dans Skype entreprise Server, vous gérez les détails de la Conférence en spécifiant les paramètres de configuration et de stratégie comme suit. Notez que les termes conférence et réunion sont parfois utilisés de manière interchangeable. Mais en règle générale, une réunion peut être considérée comme l’instance spécifique d’une conférence.
  
- **Les paramètres d’une stratégie de conférence** englobent une grande variété d’options de planification et de participation, notamment la possibilité d’utiliser des fonctions audio et vidéo IP dans une réunion et de déterminer le nombre maximal de participants. Vous pouvez utiliser les stratégies de conférence pour gérer la sécurité, la bande passante et les aspects juridiques des réunions.
    
    Notez que les stratégies de conférence sont appliquées à l’utilisateur ou au site et ne peuvent être appliquées à une réunion particulière. Par conséquent, l’invitation à la réunion de la Conférence peut être créée à l’avance quelques semaines, mais la stratégie de conférence restrictive doit être appliquée au compte Skype entreprise de l’organisateur de la réunion juste avant le début de la Conférence. 
    
    Si un compte dédié est utilisé pour le rôle de l’organisateur de la réunion, la stratégie de conférence peut rester affectée à ce compte. Si l’organisateur de la réunion utilise un compte général Skype entreprise, la stratégie doit être supprimée une fois la conférence terminée.
    
- **Les paramètres de configuration de réunion** déterminent le type de réunion que les utilisateurs peuvent créer. Ils contrôlent également, le cas échéant, la façon dont les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent se joindre aux réunions. Notez que ces paramètres affectent uniquement les réunions planifiées. Les configurations de réunion sont appliquées par pool, par site, ou globalement.
    
- Les **paramètres de configuration de conférences** déterminent des éléments tels que la taille maximale autorisée pour le contenu et les documents de la réunion. quantité maximale de bande passante pour le service de conférence de partage d’application; limites de stockage et périodes d’expiration; URL des téléchargements internes et externes du client pris en charge; pointe vers des URL internes et externes où les utilisateurs peuvent obtenir de l’aide et des ressources de conférence; les ports utilisés pour le partage d’application, le son du client, le transfert de fichiers et le trafic multimédia.
    
    Ces paramètres vous permettent de gérer les serveurs eux-mêmes. Ces paramètres ne peuvent être définis qu’à l’aide de Skype entreprise Server Management Shell. 
    
- **Les paramètres des accès aux conférences rendez-vous** vous permettent de définir des informations indiquant si, et de quelle manière les utilisateurs composent un numéro à partir d’un téléphone. Vous pouvez spécifier certaines informations d’accès aux conférences rendez-vous, telles que le numéro d’accès, dans l’onglet Conférence du Panneau de configuration et certaines informations de connexion (comme le plan de numérotation, la stratégie vocale, l’itinéraire et l’utilisation RTC) sous l’onglet Routage des communications vocales du Panneau de configuration.
    
- **Les paramètres de stratégie de code confidentiel** vous permettent de nommer et de définir le code confidentiel que les participants utilisent pour l’accès aux conférences rendez-vous.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gestion des conférences à l’aide du panneau de configuration Skype entreprise Server ou à l’aide de Skype entreprise Server Management Shell

Vous pouvez gérer la plupart des stratégies de conférence et des paramètres de configuration en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell. Certains paramètres de configuration ne sont disponibles qu’à l’aide de Skype entreprise Server Management Shell.
  
- Pour gérer les paramètres de stratégie de conférence :
    
  - dans le Panneau de configuration, sélectionnez **Conférence | Stratégie de conférence**.
    
  - dans PowerShell, recherchez les applets de commande **-CsConferencingPolicy**.
    
- Pour gérer les paramètres de configuration de réunion :
    
  - dans le Panneau de configuration, sélectionnez **Conférence | Configuration de réunion**.
    
  - Dans Skype entreprise Server Management Shell, recherchez le cmdlet **-CsMeetingConfiguration** .
    
- Pour gérer les paramètres des numéros d’accès aux conférences rendez-vous :
    
  - dans le Panneau de configuration, sélectionnez **Conférence | Numéro d’accès aux conférences rendez-vous**.
    
  - Dans Skype entreprise Server Management Shell, recherchez le cmdlet **-CsDialInConferencing** .
    
- Pour gérer les informations d’accès aux conférences rendez-vous telles que le plan de numérotation, la stratégie de voix, l’itinéraire et l’utilisation RTC : 
    
  - dans le Panneau de configuration, sélectionnez **Conférence | Routage des communications vocales**.
    
  - Dans Skype entreprise Server Management Shell, recherchez les applets **de CsDialPlan** et **-CsVoice** .
    
- Pour gérer les paramètres de stratégie de code confidentiel :
    
  - dans le Panneau de configuration, sélectionnez **Conférence | Stratégie de code confidentiel**.
    
  - Dans Skype entreprise Server Management Shell, recherchez le cmdlet **-CsPinPolicy** .
    
- Pour gérer les paramètres de configuration des conférences, vous devez utiliser Skype entreprise Server Management Shell. Recherchez les applets de commande **-CsConferencingConfiguration**.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlets Skype entreprise Server Management Shell

Pour gérer les conférences, vous pouvez utiliser les applets de commande Skype entreprise Server Management Shell suivantes: 
  
**Paramètres de stratégie de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies de conférence qui ont été configurées pour être utilisées dans votre organisation. Les stratégies de conférences déterminent les fonctionnalités pouvant être utilisées au cours des conférences ; elles indiquent par exemple si la conférence peut inclure de l’audio et de la vidéo sur IP ou encore le nombre maximal de participants à une réunion.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Affecte une stratégie de conférence au niveau de l’étendue Utilisateur.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crée une stratégie de conférence pour votre organisation.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Supprime la stratégie de conférence spécifiée.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifie une stratégie de conférence existante.  <br/> |
   
**Paramètres de configuration des réunions**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Renvoie des informations sur les paramètres de configuration de réunion actuellement utilisés dans votre organisation. Les paramètres de configuration de réunion contribuent à déterminer le type de réunion que les utilisateurs peuvent créer. Ils contrôlent en outre, le cas échéant, la façon dont les utilisateurs anonymes et les utilisateurs de conférences rendez-vous peuvent se joindre aux réunions.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de réunion au niveau de l’étendue du site ou du service. Notez que ces paramètres affectent uniquement les réunions planifiées; Il n’y a pas d’incidence sur les réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans Skype entreprise.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Supprime une collection existante de paramètres de configuration de réunion.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifie les paramètres de configuration de réunion actuellement utilisés dans votre organisation.  <br/> |
   
**Paramètres de configuration de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Renvoie des informations sur les paramètres de configuration de conférence de votre organisation. Les paramètres de conférence déterminent certains éléments comme la taille maximale autorisée des documents et du contenu de la conférence, la période de grâce du contenu (à savoir, la durée pendant laquelle le contenu sera stocké avant d’être supprimé) et les URL des téléchargements internes et externes du client pris en charge.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration de conférence.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Supprime la collection spécifiée des paramètres de configuration de conférence.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifie une collection existante de paramètres de configuration de conférence.  <br/> |
   
**Paramètres de configuration des conférences rendez-vous**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Renvoie des informations sur les annuaires de conférences configurés pour être utilisés dans votre organisation. Les annuaires des conférences permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Extrait des informations sur la façon dont Skype entreprise Server répond lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retourne des informations sur tous les numéros d’accès de conférence rendez-vous configurés en vue d’une utilisation dans votre organisation.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Renvoie les paramètres de signalisation DTMF (Dual-Tone Multifrequency ou numérotation en fréquences vocales) utilisés pour la conférence rendez-vous. Le système DTMF permet aux utilisateurs qui rejoignent une conférence d’en contrôler les paramètres (comme la capacité de mettre en sourdine ou de verrouiller ou déverrouiller la conférence) à l’aide du clavier du téléphone.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Renvoie une liste de langues, notamment les langues régionales et minoritaires, prises en charge pour les conférences rendez-vous Skype entreprise Server. Ces langues sont utilisées pour relayer les messages audio et les instructions aux utilisateurs participant à la conférence grâce à un numéro de téléphone.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retourne des informations sur les plans de numérotation utilisés au sein de votre organisation.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Affecte un plan de numérotation à un ou plusieurs utilisateurs ou groupes.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importe des annuaires de conférences de Microsoft Office Communications Server 2007 R2 vers Skype entreprise Server. Cela permet de fournir une interopérabilité entre Skype entreprise Server et Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Déplace un annuaire des conférences existant d’un pool vers un autre. Les annuaires des conférences permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crée un annuaire de conférence en vue de l’utiliser dans votre organisation. Les annuaires de conférence permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crée un nouveau numéro d’accès à la conférence rendez-vous.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de configuration pour la conférence rendez-vous. Ces paramètres déterminent le mode de réponse de Skype entreprise Server lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous. Sont renvoyées en particulier des informations qui indiquent si les participants sont tenus ou non d’enregistrer leur nom en rejoignant la conférence et comment (ou si) le système doit annoncer qu’une personne a rejoint la conférence ou l’a quittée.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crée une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crée un nouveau plan de numérotation.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Supprime un annuaire des conférences existant. Les annuaires des conférences permettent aux utilisateurs de conférence rendez-vous de rechercher plus facilement des informations sur une conférence.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Supprime un numéro d’accès à une conférence rendez-vous existant.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Supprime une ou plusieurs collections de paramètres de configuration de conférence rendez-vous. Ces paramètres déterminent le mode de réponse de Skype entreprise Server lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Supprime une collection de paramètres de signalisation DTMF (Dual Tone Multi-Frequency) utilisés pour les conférences rendez-vous.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifie les valeurs de propriétés d’un numéro d’accès de conférence rendez-vous existant. La conférence rendez-vous permet aux utilisateurs d’utiliser un téléphone fixe ou mobile ou tout autre périphérique sur le réseau téléphonique public commuté (RTC) pour rejoindre la partie audio d’une conférence.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifie les paramètres qui déterminent la façon dont Skype entreprise Server répond lorsque les utilisateurs rejoignent ou quittent une conférence rendez-vous.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifie les paramètres de signalisation DTMF (Dual Tone Multi-Frequency) de la conférence rendez-vous.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifie un plan de numérotation existant.  <br/> |
   
**Paramètres de stratégie de code confidentiel**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Renvoie des informations sur les stratégies d’authentification par code confidentiel des clients configurées pour être utilisées dans votre organisation. L’authentification de code confidentiel permet aux utilisateurs d’accéder à Skype entreprise Server en fournissant un code confidentiel au lieu d’un nom d’utilisateur et d’un mot de passe.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Affecte une stratégie cliente de code confidentiel à un utilisateur ou un groupe d’utilisateurs.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crée une stratégie d’authentification par code confidentiel pour les clients.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Supprime la stratégie de code confidentiel.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifie une ou plusieurs stratégies d’authentification par code confidentiel existantes pour les clients.  <br/> |
   
**Autres paramètres de conférence**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Désactive une salle de réunion Skype entreprise Server. Une salle de réunion est un appareil de conférence conçu pour répondre aux besoins de conférences vidéo et de collaboration dans des petites salles de conférence. Lorsque vous désactivez un objet salle de réunion, vous supprimez tous les attributs Active Directory spécifiques de Skype entreprise attribués au compte d’utilisateur qui représente la salle de réunion. Toutefois, le compte d’utilisateur Active Directory proprement dit n’est pas supprimé.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Active une salle de réunion Skype entreprise Server. Pour activer une salle de réunion, vous devez d’abord créer un compte d’utilisateur Active Directory qui représentera ce système. Notez que, même si les objets salle de réunion sont basés sur les comptes d’utilisateurs, ces objets n’apparaissent pas lorsque vous exécutez l’applet de commande Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Renvoie des informations sur la notification d’exclusion des conférences utilisée dans votre organisation. La notification d’exclusion des conférences est un message qui s’affiche pour les utilisateurs qui rejoignent la conférence à l’aide d’un lien hypertexte (par exemple, les utilisateurs qui collent un lien d’accès à la conférence dans un navigateur tel que Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Renvoie des informations sur l’ensemble des salles de réunion Skype entreprise Server configurées pour une utilisation au sein de l’organisation.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Déplace un objet salle de réunion Skype entreprise Server d’un pool d’inscriptions vers un autre.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Efface le texte de l’en-tête et du corps de la notification d’exclusion des conférences utilisée dans votre organisation. La notification d’exclusion des conférences est un message qui s’affiche pour les utilisateurs qui rejoignent la conférence à l’aide d’un lien hypertexte (par exemple, les utilisateurs qui collent un lien d’accès à la conférence dans un navigateur tel que Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifie les valeurs de propriétés d’une salle de réunion Skype entreprise Server existante.  <br/> |
   
**Paramètres de test**

|**Applet de commande**|**Description**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Teste l’aptitude d’une paire d’utilisateurs à prendre part à une conférence de partage d’application.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Effectue un test pour déterminer si un utilisateur peut se connecter à son fournisseur de services d’audioconférence. Un fournisseur de services d’audioconférence est une société tierce qui propose des services de conférence aux entreprises. Entre autres, il permet aux utilisateurs localisés hors site et non connectés au réseau de l’entreprise ou à Internet, de participer à la partie audio d’une conférence ou d’une réunion.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Teste l’aptitude de deux utilisateurs à prendre part à une conférence audio/vidéo (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Vérifie si une seule paire d’utilisateurs peut participer à une conférence Web Skype entreprise Server incluant des activités telles que le partage ou l’affichage de diapositives PowerPoint, de tableaux blancs ou de sondages. L’applet de passe vérifie également que le service de conférence Web de Skype entreprise Server peut découvrir Office Web Apps Server et qu’un client peut télécharger un fichier PowerPoint pour diffusion par le biais d’Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Vérifie si un utilisateur peut participer à une session de conférence rendez-vous.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Teste un numéro de téléphone par rapport à un plan de numérotation (anciennement appelé « profil d’emplacement ») et retourne la règle de normalisation qui sera appliquée au numéro, ainsi que le numéro traduit après application de la règle de normalisation.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Teste la possibilité pour trois utilisateurs de participer à une conférence de service de mobilité Skype entreprise Server. Le service de mobilité permet aux utilisateurs de téléphones mobiles tels que les iPhone et les téléphones Windows de faire des choses telles que des messages instantanés et des informations de présence Exchange. stocker et récupérer des messages vocaux en interne plutôt qu’avec leur opérateur sans fil; Tirez parti des fonctionnalités de Skype entreprise Server (appel par poste de travail et Conférence rendez-vous).  <br/> **Remarque:** Les clients qui utilisent MCX ne sont pas pris en charge dans Skype entreprise Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Teste la capacité de deux utilisateurs à planifier, participer à et mener une conférence en ligne à l’aide de l’API web Communications unifiées (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Renvoie les informations de diagnostic relatives aux fonctionnalités de conférence de données incluses dans Skype entreprise Server.  <br/> |
   

