---
title: 'Audit de l’application Patients pour Teams administrateurs informatiques et de conformité '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: En savoir plus sur l’audit de l’application Patients pour Teams administrateurs
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b65dae205f7f7438482847ceb07e37a64609a534
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595058"
---
# <a name="audit-logs-for-patients-app"></a>Journaux d’audit pour l’application Patients

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui soutien l’équipe. Toutes les données associées à l’application Patients sont conservées dans ce groupe mais ne sont plus accessibles via l’interface utilisateur. Les utilisateurs peuvent re-créer leurs listes à l’aide de l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Les listes permet aux équipes de soins de votre organisation de santé de créer des listes de patients pour différents scénarios (arrondis, réunions d’équipe de formation, surveillance générale des patients, etc.). Pour commencer, consultez le modèle Patients dans listes. Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, consultez [Gérer l’application Listes](../../manage-lists-app.md).

Un journal d’audit pour l’activité de l’application Patients permet aux équipes de réponse après incident d’examiner les modifications apportées aux dossiers médicaux électroniques (EMR) ou aux informations médicales des patients (PHI) d’un patient, et de déterminer si des modifications ou améliorations de la stratégie ou de la procédure d’accès à PHI dans les outils de productivité sont nécessaires. Les événements du journal d’audit couvrent les actions effectuées via l’interface utilisateur de l’application Patients.

## <a name="meet-hipaa-requirements"></a>Répondre aux exigences de la loi américaine HIPAA

Conformément aux directives de l’HIPAA, les fournisseurs de soins de santé doivent conserver des enregistrements de tout accès à PHI, afin que les modifications soient auditées. Microsoft s’engage à ce que ses clients d’entreprise utilisent Microsoft Teams et à leur aider à répondre aux exigences et contrôles de la loi américaine HIPAA. L’accès à PHI via l’application Patients est entièrement suivi et les journaux [](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) sont disponibles dans le Centre de conformité Microsoft 365, comme décrit dans l’article sur les fonctionnalités de recherche dans le journal d’audit.

> [!IMPORTANT]
> La charge de la confidentialité des patients est placée par la loi sur le fournisseur de soins de santé. Cette loi donne droit à la vie privée des patients et exige qu’un administrateur informatique ou un contrôleur HIPAA puisse déterminer aisément l’infirmière, l’infirmière ou le collaborateur social qui a accédé aux dossiers des patients ou les a modifiés. L’accès aux patients VIP est l’un des exemples les plus courants de violations d’accès PHI. La fonctionnalité du journal d’audit est requise pour effectuer des enquêtes sur toute violation d’accès PHI et pour répondre aux exigences de la loi américaine HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Activer les journaux d’audit pour l’application Patients

Un audit dépend de plusieurs configurations antérieures :

1. L’administrateur doit travailler avec son fournisseur de services FEMBA pour que EMR utilise un format utilisé par l’application Patients. 
2. Un administrateur de fournisseur de soins doit activer l’application Patients dans Teams d’administration. Pour plus [d’informations,](../../teams-app-setup-policies.md) voir Gérer les stratégies de configuration Microsoft Teams et les articles connexes.
3. L’administrateur doit activer les audits d’activité de la même [](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) façon qu’ils activent n’importe quel audit du journal d’activité, comme décrit dans la page Avant de commencer et d’activer ou désactiver la recherche dans le journal [d’audit.](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Si l’enregistrement d’audit est déjà en cours, rien de particulier n’est nécessaire pour l’application Patients. Chaque fois qu’un fournisseur de soins de santé installe et exécute l’application au sein d’une équipe, les journaux d’audit enregistrent leur activité PHI.
4. L’administrateur doit alors annoncer la disponibilité de l’application Patients et les travailleurs de la santé doivent commencer à générer l’activité à inclure dans un audit.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Exécuter un audit

Pour obtenir des instructions sur l’exécution d’une recherche dans le journal d’activité, voir [Rechercher dans le journal d’audit.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Activités enregistrées pour l’application Patients

L’application Patients possède ses propres activités journalées, répertoriées dans le tableau suivant :

|Nom convivial | Opération | Description|
|:---|:---|:---|
| Liste des patients | PatientListView | Un utilisateur a vu la liste des patients.|
| Liste des patients supprimés | PatientListDelete | Un utilisateur a supprimé une liste de patients.|
| Patient ajouté à la liste | PatientListAddListent | Un patient a été ajouté à la liste des patients. |
| Ajout d’une note pour un patient | PatientNoteAdd | Une note a été ajoutée à un dossier de patients. |
| Schéma de patient créé | PatientSchemaCreate | Un ensemble de colonnes utilisées dans l’enregistrement du patient a été créé. |
| Un utilisateur a initié une exportation | ExportInitiation | Les données des patients ont été exportées de l’application Patients vers Excel fichier. Le fichier est enregistré dans le site de la SharePoint’équipe. |
| Liste des patients créée | PatientListCreate | Un utilisateur a créé une liste de patients.|
| Définir la liste des patients par défaut| PatientListDefaultSet| Un utilisateur a définir une liste particulière en tant que liste par défaut.|
| Patient supprimé de la liste| PatientListRemoveSent | Un patient a été supprimé de la liste des patients. |
| Patient recherché | PatientSearch | A recherché un dossier de patient dans le service EHR. |
| Schéma patient mis à jour | PatientSchemaUpdate  | Mise à jour d’un ensemble existant de colonnes utilisées dans l’enregistrement du patient. |<!-- | Patient déplacé vers une autre liste| PatientMoved | L’enregistrement d’un patient a été déplacé d’une liste à l’autre. |-->
| Liste des patients renommés | PatientListRename | Une liste de patients a été renommée. |
| Colonnes modifiées dans la liste des patients | PatientListEditColumns | Une colonne d’une liste de patients a été modifiée (ajoutée ou supprimée). |
| Détails sur le patient | PatientView | Un utilisateur a vu un dossier de patient.|
| Détails du patient modifié | PatientDetailsEdit | Les détails d’un dossier de patients ont été modifiés. |
| Définir la connexion EHR | EHRConnectionSet | Définissez l’URL utilisée pour se connecter à la connexion du service FEMBA. Exemple : https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |

Vous pouvez personnaliser votre audit selon vos besoins pour rechercher ou filtrer sur l’une de ces activités journalées.

Les activités enregistrées pour Microsoft Teams en général sont décrites dans Microsoft Teams [activités.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Rubriques connexes

[Effectuer des recherches dans le journal d’audit](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
