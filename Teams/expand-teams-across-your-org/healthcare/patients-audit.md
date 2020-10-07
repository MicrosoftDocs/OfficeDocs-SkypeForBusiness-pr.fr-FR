---
title: 'Audit de l’application patients pour les administrateurs informatiques et responsables de la conformité '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Application patients pour les administrateurs teams
ms.openlocfilehash: 9e4ec8179fda091fcd2ecd047d633b5bda6026b6
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367694"
---
# <a name="audit-logs-for-patients-app"></a>Journaux d’audit pour l’application Patients

> [!IMPORTANT]
> **À compter du 30 octobre 2020, l’application patients sera déconseillée et les utilisateurs ne pourront plus l’installer à partir de l’App Store d’Teams. Nous vous encourageons à commencer à utiliser l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans teams dès aujourd’hui.**
>
>Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe. Lorsque l’application patients est supprimée, toutes les données qui lui sont associées seront conservées dans ce groupe, mais ne seront plus accessibles par le biais de l’interface utilisateur. Les utilisateurs actuels peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>L' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) est préinstallée pour tous les utilisateurs d’teams et est disponible sous la forme d’une tabulation dans chaque équipe ou canal. Les listes permettent aux équipes de soins de créer des listes de patients à l’aide du modèle de patients intégré, de zéro à partir de zéro ou d’importer des données dans Excel. Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).

Le journal d’audit de l’activité des applications patient permet aux équipes de réponse après incident de passer en revue les modifications apportées aux dossiers médicaux électroniques d’un patient ou aux informations médicales du patient (PHI) et de déterminer si des modifications ou des améliorations apportées à la politique ou la procédure pour l’accès PHI dans les outils de productivité sont nécessaires. Les événements du journal d’audit traitent les actions effectuées par le biais de l’interface utilisateur de l’application patients.

## <a name="meet-hipaa-requirements"></a>Respecter la loi HIPAA

Conformément aux directives du HIPAA, les prestataires de services de santé doivent conserver des enregistrements de tout accès à la norme PHI, de sorte que les modifications soient auditées. Microsoft s’engage à remplir ses clients d’entreprise à l’aide de Microsoft Teams, et de les aider à répondre aux exigences et contrôles HIPAA. L’accès à la fonction PHI par le biais de l’application patients est entièrement suivi et les journaux sont rendus disponibles dans le centre de conformité Microsoft 365, comme décrit dans l’article [fonctionnalité de recherche du journal d’audit](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) .

> [!IMPORTANT]
> La charge de la mise en place de la vie privée du patient est appliquée au service de santé par la Loi. La législation donne lieu à la vie privée et exige qu’un administrateur informatique ou un contrôleur d’HIPAA puisse facilement identifier le niveau d’infirmier, du praticien ou du travailleur social ayant consulté ou modifié les dossiers du patient. L’un des exemples les plus courants d’une violation d’accès PHI est l’accès aux patients VIP. La fonctionnalité du journal d’audit est nécessaire pour effectuer des enquêtes sur une violation d’accès PHI et répondre aux exigences du HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Activer les journaux d’audit pour l’application patients

Un audit dépend de plusieurs configurations antérieures :

1. L’administrateur doit collaborer avec son fournisseur de services FHIR pour qu’il utilise EMR dans un format utilisé par l’application patients. Voir [intégration des enregistrements de santé électronique dans Microsoft teams](patients-app.md).
2. Un administrateur de prestataire de services de santé doit activer l’application patients dans le centre d’administration Teams. Pour plus d’informations, consultez [gérer les stratégies de configuration des applications dans Microsoft teams](../../teams-app-setup-policies.md) et les Articles connexes.
3. L’administrateur doit activer les audits d’activité, de la même manière qu’il s’agit de l’activation de l’audit du journal d’activité, comme décrit dans la section [avant de commencer](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) et [activer ou désactiver la recherche dans le journal d’audit](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search). Si la journalisation d’audit est déjà activée, rien de spécial n’est nécessaire pour l’application patients. Chaque fois qu’un fournisseur de services de santé installe et exécute l’application au sein d’une équipe, les journaux d’audit enregistrent l’activité PHI.
4. L’administrateur doit alors annoncer la disponibilité de l’application patients, et les travailleurs de la santé doivent commencer à générer une activité qui sera incluse dans un audit.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Exécuter un audit

Pour obtenir des instructions sur l’exécution d’une recherche du journal d’activité, voir [effectuer une recherche dans le journal d’audit](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

## <a name="logged-activities-for-patients-app"></a>Activités journalisées pour l’application patients

L’application patients possède ses propres activités journalisées, répertoriées dans le tableau suivant :

|Nom convivial |Opération|Description|
|:---|:---|:---|
| Affichage de la liste des patients | PatientListView | Un utilisateur a consulté une liste de patients.|
| Liste des patients supprimés | PatientListDelete | Un utilisateur a supprimé une liste de patients.|
| Le patient a été ajouté à la liste | PatientListAddPatient | Un patient a été ajouté à une liste de patients. |
| Note ajoutée pour le patient | PatientNoteAdd | Une note a été ajoutée à un enregistrement patient. |
| Création du schéma du patient | PatientSchemaCreate | Un ensemble de colonnes utilisé dans l’enregistrement patient a été créé. |
| L’utilisateur a initié une exportation | ExportInitiation | Les données du patient ont été exportées à partir de l’application patients dans un fichier Excel. Le fichier est enregistré sur le site SharePoint de l’équipe. |
| Création de la liste des patients | PatientListCreate | Un utilisateur a créé une liste de patients.|
| Définir la liste de patients par défaut| PatientListDefaultSet| Un utilisateur a défini une liste particulière en tant que liste par défaut.|
| A supprimé un patient de la liste| PatientListRemovePatient | Un patient a été supprimé d’une liste de patients. |
| Recherche du patient | PatientSearch | Recherche d’un dossier patient dans le service DMI. |
| Mise à jour du schéma du patient | PatientSchemaUpdate  | Mise à jour d’un ensemble existant de colonnes utilisées dans l’enregistrement patient. |!--< | Déplacement du patient vers une autre liste| PatientMoved | L’enregistrement du patient a été déplacé d’une liste vers une autre. |-->
| Liste renommée patient | PatientListRename | Une liste de patients a été renommée. |
| Colonnes modifiées dans la liste des patients | PatientListEditColumns | Une colonne dans une liste de patients a été modifiée (ajoutée ou supprimée). |
| Détails du patient consultés | PatientView | Un utilisateur a consulté un dossier patient.|
| Modification des détails du patient | PatientDetailsEdit | Le détail d’un enregistrement patient a été modifié. |
| Définir la connexion DMI | EHRConnectionSet | Définissez l’URL utilisée pour la connexion à la connexion au service DMI FHIR. Par exemple : https://<span>API-V8-dstu2.hspconsortium.org/ContosoHospital/Open</span>  |
||||

Vous pouvez personnaliser votre audit selon vos besoins pour effectuer une recherche ou un filtrage sur une de ces activités journalisées.

Les activités journalisées de Microsoft teams sont décrites dans [activités de Microsoft teams](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities).

## <a name="related-topics"></a>Sujets associés

[Effectuer une recherche dans le journal d’audit](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Intégration des dossiers médicaux électroniques dans Microsoft Teams](patients-app.md)
