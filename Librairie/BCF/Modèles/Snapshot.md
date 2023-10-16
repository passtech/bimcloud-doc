Le modèle des screenshots


Snapshot {

		Le type du snapshot
        snapshot_type: Snapshot.SnapshotTypeEnum,

		Les données du snapshot
        snapshot_data: string
}


Typage du snapshot_type
namespace Snapshot {

    export type SnapshotTypeEnum = 'jpg' | 'png';
    
    export const SnapshotTypeEnum = {
        Jpg: 'jpg' as SnapshotTypeEnum,
        Png: 'png' as SnapshotTypeEnum
    };
}