# Cài đặt - Installation

Cài đặt package respeaker_ros

Clone package về máy.


# Vận hành 

Để khởi động Microphone array, chạy file launch: 

$ roslaunch respeaker_ros respeaker.launch 

File này chạy sẽ xuất các  kết quả ra các topic: 
    rostopic echo /sound_direction     # Result of DoA 
    rostopic echo /sound_localization  # Result of DoA as Pose 
    rostopic echo /is_speeching        # Result of VAD 
    rostopic echo /audio               # Raw audio 
    rostopic echo /speech_audio        # Audio data 
    rostopic echo /speech_to_text      # Result of recognition

## Task robot quay về phía người gọi

Từ khóa: "hi"

Tác dụng: Khi người ở hướng nào nói "Hi" thì robot quay về hướng đó.
catkin_make lại catkin_ws: 

```
cd ~/catkin_ws 
catkin_make 
```
 

### Chạy mô phỏng trên gazebo: 
Sau khi tải về nếu đổi tên folder từ speech_to_text thành speech_rotate thì chạy lệnh dưới
`roslaunch speech_rotate gazebo-word-rotate.launch`
Nếu muốn giữ nguyên tên folder speech_to_text thì phải vào file CMakeLists.txt và Packages.xml sửa lại các tên speech_rotate thành speech_to_text rồi chạy lệnh dưới đây
`roslaunch speech_to_text gazebo-word-rotate.launch`
 
### Chạy trên robot thực tế: 

`roslaunch speech-rotate word-rotate.launch`

 

Lưu ý:  đặt microphone array  ở chính  giữa robot,  jack cắm dây nguồn và dây  audio hướng  thẳng ra phía  mặt trước robot (vì  lấy  làm gốc tọa  độ) 


## Task robot 
